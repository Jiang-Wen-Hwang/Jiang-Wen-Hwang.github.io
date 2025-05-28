# Chapter 8 異質變異數（Heteroskedasticity）

## 1 & 2. 殘差圖視覺化

Step 1：以 OLS 估計並取得殘差 $\hat{u}_{i}$ 與擬合值 $\hat{y}_{i}$。
Step 2：繪製散點圖—(a) $\hat{u}_{i}$ 對 $\hat{y}_{i}$，或 (b) $\hat{u}_{i}$ 對主要自變數 $x_{i}$。
Step 3：若點雲呈「漏斗形」或變動幅度隨 $\hat{y}_{i}$/$x_{i}$ 擴大縮小，即顯示異質變異數。

## 3. 檢定異質變異數

* **Breusch–Pagan (BP)**：回歸 $\hat{u}_{i}^{\,2}$ 對解釋變數，計算 $nR^{2}\sim\chi^{2}_{k}$。
* **White**：在 BP 模型中加入平方與交乘項。

## 4. 解決方案

1. 變數轉換：若 $\operatorname{Var}(u_{i})=\sigma^{2}h(z_{i})$。
2. **加權最小平方 (WLS)**。
3. **HC 標準誤**。

## 5. HC 標準誤公式

$$
\widehat{\operatorname{Var}}\!\bigl(\hat{\beta}\bigr)
 =(X'X)^{-1}\Bigl(\sum_{i=1}^{n}\hat{u}_{i}^{\,2}x_{i}x_{i}'\Bigr)(X'X)^{-1}.
$$

## 6. GLS

若已知 $\Omega$，左右乘 $\Omega^{-\tfrac12}$ 後 OLS。

## 7. FGLS

用 OLS 殘差估 $\Omega$，再 GLS，必要時迭代。

---

# Chapter 10 內生性與工具變數（Endogeneity & IV）

## 1. 殘差圖辨識內生性

Step 1：以 OLS 得 $\hat{u}$。
Step 2：繪製 $\hat{u}$ 對可疑 $x$ 散點圖。
Step 3：若相關則 $\operatorname{Cov}(x,u)\neq0$。

## 2. 內生性的定義

當 $\operatorname{Cov}(x,u)\neq0$ 時，$x$ 為內生。

## 3. 可識別模型與內生性來源

* **可識別**：結構參數可唯一辨識。
* **來源**：省略變數、同時性、測量誤差、反向因果。

## 4. 影響

OLS 偏誤且不一致。

## 5. 工具變數三要件

1. 關聯性：$\operatorname{Cov}(z,x)\neq0$
2. 外生性：$\operatorname{Cov}(z,u)=0$
3. 排除：$z$ 僅經由 $x$ 影響 $y$

## 6. 識別條件

* 階條件
* 秩條件

## 7. 估計方法

2SLS：第一階段 $x\sim Z$ → $\hat{x}$；第二階段 $y\sim\hat{x}$。

## 8. 內生性檢定 (DWH)

$$
H=(\hat{\beta}_{\text{OLS}}-\hat{\beta}_{\text{IV}})'
    [\widehat{\operatorname{Var}}(\hat{\beta}_{\text{IV}})
    -\widehat{\operatorname{Var}}(\hat{\beta}_{\text{OLS}})]^{-1}
    (\hat{\beta}_{\text{OLS}}-\hat{\beta}_{\text{IV}}).
$$

## 9. 弱工具檢定

第一階段 $F>10$；或 Kleibergen–Paap rk Wald。

## 10. 工具有效性 (Sargan/Hansen)

$J=nR^{2}\sim\chi^{2}_{(q-p)}$。

## 11. 異質變異數下的 IV

使用 robust SE 或 GMM 權重。

---

# Chapter 11 聯立方程式與 2SLS

## 1. 簡化型推導

$$
BY+\Gamma X=u
\quad\Longrightarrow\quad
Y=-B^{-1}\Gamma X+B^{-1}u=\Pi X+v.
$$

## 2–3. 識別條件

階條件與秩條件。

## 4. 2SLS

Stage 1：$\hat{X}=Z(Z'Z)^{-1}Z'X$。
Stage 2：$y\sim\hat{X}$。

---

# Chapter 15 Panel Data

## 1. Pooled Model

$$
y_{it}=\beta' x_{it}+u_{it}.
$$

## 2. 估計量

* FD：$\Delta y_{it}=\beta\Delta x_{it}+\Delta u_{it}$
* Within：$y_{it}-\bar{y}_{i}=\beta(x_{it}-\bar{x}_{i})+u_{it}-\bar{u}_{i}$
* FE：加入固定效果虛擬變數

## 3. 固定效果模型

$$
y_{it}=\alpha_{i}+\beta x_{it}+u_{it}.
$$

## 4. 隨機效果

$$
\theta=1-\bigl(1+T\sigma_{\alpha}^{2}/\sigma_{u}^{2}\bigr)^{-1/2}.
$$

## 5. FE F-test

$$
F=\frac{(SSR_{P}-SSR_{FE})/(N-1)}
          {SSR_{FE}/[N(T-1)-k-N+1]}.
$$

## 6. RE LM test

$$
\text{LM}=\frac{T}{2}\sum_{i=1}^{N}
\left(\frac{\hat{u}_{i}^{\,2}}{\hat{\sigma}^{2}}\right)^{2}\sim\chi^{2}_{1}.
$$

## 7. 內生性檢定

Hausman 比較 $\hat{\beta}_{\text{RE}}$ 與 $\hat{\beta}_{\text{FE}}$。

## 8. Hausman–Taylor

允許部分 $x$ 與 $\alpha_{i}$ 相關，利用 $\bar{x}_{i}$ 作工具。

## 9. 異質變異數

用 cluster-robust、HAC 或 PCSE。

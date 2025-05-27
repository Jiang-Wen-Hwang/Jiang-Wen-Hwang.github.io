# Chapter 8/10/11/15 Reference Table (Optimized for GitHub Markdown)

|   章節 | 主題                       | 模型 / 定理                                     | 內容說明                                 | 估計式 / 檢定式               | 虛無假設 H₀                     | 要點 / 備註                        |
|-------:|:---------------------------|:------------------------------------------------|:-----------------------------------------|:------------------------------|:--------------------------------|:-----------------------------------|
|      8 | 異質變異回歸模型           | [詳見模型 / 定理]                               | 允許誤差變異隨解釋變數系統性改變         | —                             | —                               | 後續 GLS、檢定基礎                 |
|      8 | White (HC0–HC3) 穩健變異數 | [詳見模型 / 定理]                               | 不需事先知道 $h(x)$；大樣本一致          | HC1、HC2、HC3 只對 HC0 再加權 | —                               | t/F/信賴區間在有無異質變異時皆有效 |
|      8 | GLS（已知變異）            | [詳見模型 / 定理]                               | 加權最小平方法 (WLS) 與 GLS 等價         | [詳見估計式 / 檢定式]         | —                               | 假設正確時為 BLUE                  |
|      8 | FGLS（未知變異）           | [詳見模型 / 定理]                               | OLS→估 $\alpha$→得 $\hat{h}(z_i)$→WLS    | 同左                          | —                               | 一致且通常效率高於 OLS             |
|      8 | Goldfeld–Quandt            | [詳見模型 / 定理]                               | 分組比較誤差變異                         | 同左                          | $H_0:\sigma_1^{2}=\sigma_2^{2}$ | 樣本可自然排序或分割               |
|      8 | Breusch–Pagan / LM         | [詳見模型 / 定理]                               | $LM=nR^{2}\xrightarrow{d}\chi^{2}_{S-1}$ | 同左                          | $H_0:\alpha_2=\dots=\alpha_S=0$ | 檢測誤差變異是否隨 $z$ 改變        |
|      8 | White 全域檢定             | 以 $x, x^{2}$ 與交乘項做 $z$                    | 同 BP，但對任意異質變異具一致性          | 同 BP                         | 同 BP                           | 亦可偵測模型型態錯誤               |
|     10 | 內生性問題                 | [詳見模型 / 定理]                               | 解釋變數相關 → OLS 偏誤、不一致          | —                             | —                               | 需 IV/2SLS                         |
|     10 | 工具變數 (IV)              | [詳見模型 / 定理]                               | 工具需同時滿足關聯性與外生性             | 同左                          | —                               | 單工具 just‑ID, 多工具 over‑ID     |
|     10 | 二階段最小平方 (2SLS)      | [詳見模型 / 定理]                               | 實務計算 IV 的標準流程                   | 同左                          | —                               | 軟體自動產出 SE                    |
|     10 | 弱工具檢驗                 | $F_{\text{1st stage}}>10$ (單內生)              | F 小 ⇒ weak IV                           | $F$ 統計量                    | $H_0:$ 工具弱                   | 多內生⇒Cragg–Donald $F$            |
|     10 | Hausman 檢定               | [詳見模型 / 定理]                               | $H\sim\chi^{2}_{K_{endog}}$              | 同左                          | $H_0:\operatorname{cov}(x,e)=0$ | 拒絕 ⇒ 採用 IV                     |
|     10 | Sargan/Hansen 過度識別     | [詳見模型 / 定理]                               | 檢定多餘工具是否外生                     | 同左                          | $H_0:$ 所有工具外生             | 拒絕 ⇒ 至少一工具無效              |
|     11 | 需求-供給模型              | [詳見模型 / 定理]                               | P, Q 內生 → 同時方程式                   | —                             | —                               | 須系統估計                         |
|     11 | 縮減式                     | [詳見模型 / 定理]                               | 解內生變數為外生函數                     | 式 (11.4)(11.5)               | —                               | π 可 OLS 估後生成工具              |
|     11 | 識別條件                   | 階層條件: $K^{*}\ge M_1$\n秩條件: rank$(Z)$足夠 | 確保結構參數可唯一識別                   | —                             | —                               | $K^{*}$: 外生排除數                |
|     11 | 2SLS (系統)                | [詳見模型 / 定理]                               | Stage‑1 以外生變數產出 $\hat{X}$         | 同左                          | —                               | 多方程皆適用                       |
|     11 | LIML (k‑class)             | [詳見模型 / 定理]                               | k=λ̂ (最小特徵根) ⇒ LIML                  | —                             | —                               | 小樣本偏誤較小                     |
|     15 | 固定效果 (Within)          | [詳見模型 / 定理]                               | 消除個體不變異質 $u_i$                   | OLS + cluster‑robust SE       | —                               | 無法估時間不變變數                 |
|     15 | 隨機效果 (RE)              | [詳見模型 / 定理]                               | u_i 視為隨機，FGLS 最有效                | [詳見估計式 / 檢定式]         | —                               | θ=1 ⇒ FE, θ=0 ⇒ OLS                |
|     15 | LM 檢定 (RE)               | [詳見模型 / 定理]                               | 檢測 $σ_u^{2}=0$                         | 同左                          | $H_0:σ_u^{2}=0$                 | LM>臨界 ⇒ 用 RE                    |
|     15 | Hausman (FE vs RE)         | [詳見模型 / 定理]                               | 檢驗 cov(u,x)=0                          | 同左                          | $H_0:$ RE 一致 (外生)           | 拒絕 ⇒ FE 合適                     |

---

[詳見模型 / 定理]: `$y_i=\beta_1+\beta_2x_i+e_i,\;\; \operatorname{Var}(e_i\mid x_i)=\sigma_i^{2}=\sigma^{2}h(x_i)$`

[詳見模型 / 定理]: `$\widehat{\operatorname{Var}}(\hat{\beta})_{\text{HC0}}=(X'X)^{-1}\!\Bigl(\sum_{i=1}^{n}\hat{e}_i^{2}x_ix_i'\Bigr)(X'X)^{-1}$`

[詳見模型 / 定理]: `$\sigma_i^{2}=\sigma^{2}x_i \;\Rightarrow\; y_i^{*}=\dfrac{y_i}{\sqrt{x_i}},\; x_i^{*}=1,\sqrt{x_i}$`

[詳見估計式 / 檢定式]: `$\hat{\beta}_{\text{GLS}}=(X^{*'}X^{*})^{-1}X^{*'}y^{*}$`

[詳見模型 / 定理]: `$\ln\hat{\sigma}_i^{2}=\alpha_1+\alpha_2z_{i2}+…+\alpha_S z_{iS}$`

[詳見模型 / 定理]: `$GQ=\dfrac{\text{RSS}_{1}/df_1}{\text{RSS}_{2}/df_2}\sim F(df_1,df_2)$`

[詳見模型 / 定理]: `$\hat{e}_i^{2}=\alpha_1+\sum_{s=2}^{S}\alpha_s z_{is}+v_i$`

[詳見模型 / 定理]: `$y_i=\beta_1+\beta_2x_i+e_i,\;\; \operatorname{cov}(x_i,e_i)\neq0$`

[詳見模型 / 定理]: `$\hat{\beta}_{\text{IV}}=\dfrac{\operatorname{cov}(z,y)}{\operatorname{cov}(z,x)}$`

[詳見模型 / 定理]: `Step 1: $\hat{x}=P_Zx,\; P_Z=Z(Z'Z)^{-1}Z'$\nStep 2: $\hat{\beta}_{2SLS}=(X'\!P_ZX)^{-1}X'\!P_Zy$`

[詳見模型 / 定理]: `$H=(b_{OLS}-\hat{\beta}_{IV})^{\!\prime}\!\bigl[\widehat{\operatorname{Var}}(b_{OLS})-\widehat{\operatorname{Var}}(\hat{\beta}_{IV})\bigr]^{-1}(b_{OLS}-\hat{\beta}_{IV})$`

[詳見模型 / 定理]: `$J=\hat{e}_{IV}'Z(Z'Z)^{-1}Z'\hat{e}_{IV}\xrightarrow{d}\chi^{2}_{L-B}$`

[詳見模型 / 定理]: `Demand: $Q_i=\alpha_1P_i+\alpha_2X_i+e_{di}$\nSupply: $Q_i=\beta_1P_i+e_{si}$`

[詳見模型 / 定理]: `$P_i=\pi_1X_i+v_{1i},\;\; Q_i=\pi_2X_i+v_{2i}$`

[詳見模型 / 定理]: `$\hat{\beta}_{2SLS}=(X'\!P_ZX)^{-1}X'\!P_Zy$`

[詳見模型 / 定理]: `$\hat{\beta}_{k}=\bigl(X'(I-kM)X\bigr)^{-1}X'(I-kM)y$`

[詳見模型 / 定理]: `$y_{it}-\bar{y}_i=\beta\bigl(x_{it}-\bar{x}_i\bigr)+\bigl(e_{it}-\bar{e}_i\bigr)$`

[詳見模型 / 定理]: `$y_{it}=\beta x_{it}+u_i+e_{it},\;\; \operatorname{cov}(u_i,x_{it})=0$`

[詳見估計式 / 檢定式]: `$\theta=1-\sqrt{\dfrac{\sigma_e^{2}}{\sigma_e^{2}+T\sigma_u^{2}}}$\n$y^*=y_{it}-\theta\bar{y}_i$`

[詳見模型 / 定理]: `$LM=\dfrac{N(T-1)}{2(T-2)}\Bigl[\dfrac{\sum_{i}\bigl(\sum_{t}e_{it}\bigr)^{2}}{\sum_{it}e_{it}^{2}}-1\Bigr]\xrightarrow{d}\chi^{2}_{1}$`

[詳見模型 / 定理]: `$H=(b_{FE}-b_{RE})' \bigl[\widehat{\operatorname{Var}}(b_{FE})-\widehat{\operatorname{Var}}(b_{RE})\bigr]^{-1}(b_{FE}-b_{RE})\sim\chi^{2}_{K}$`
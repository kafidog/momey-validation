# Agent 與交付治理

本文件定義此 Repository 的預設 AI/Codex 執行流程。它只統一「怎麼工作」，不覆蓋專案既有的產品、安全、授權、隱私、發布或技術限制；若其他專案文件有更嚴格規則，以更嚴格者為準。

## Astra Era
- `Astra Medium`：新專案、新 Phase、重大方向改變、重複失敗或 Final Review 才進場；負責全局理解、架構、P0/P1/P2、Delivery Issue、依賴、Gate 與風險。
- `Sol High`：執行期監督、Review、Evidence、Git/Scope 與 Final Gate。
- `Luna MAX`：主要 implementation、research、tests、fixes、documentation、evidence。
- 升級：`Luna MAX → Sol High → Astra Medium → Astra High → Astra XHigh`；High/XHigh 僅真正僵局或高風險不可逆決策。

## Goal → Delivery Issue → Codex/Luna → Evidence → Sol Gate
- 一個 Delivery Issue = 一條真人可使用、可驗收、可獨立交付的完整流程，不拆微型 Issue 海。
- 正常只讀：永久規則 + 唯一最新 handoff + 當前最高優先且已解除阻塞的 Delivery Issue。
- 同一時間只執行一個 Delivery Issue；小型已定位修復可直接最小修改、驗證、提交，不為形式另開 Issue。

## 交付優先
- 不重做已驗收內容；產品修改先最小相關測試，交付前一次必要整體驗證；純文件/治理修改不重跑產品測試。
- 同一失敗假設最多兩次無進展嘗試；分類只用 `PRODUCT`、`VALIDATION`、`EXTERNAL`、`HUMAN_AUTH`、`EVIDENCE_INSUFFICIENT`。
- 只有登入、OAuth、2FA、CAPTCHA、條款、人工授權、目前環境無法控制的實體裝置或真正外部事件才算 HUMAN_AUTH/EXTERNAL。
- 保留既有資料、憑證、授權、修改與 dirty work；禁止為了乾淨而 reset/clean/覆蓋。

## 共享能力
依序查 Registry technical_stable → experimental → 專案既有能力 → 官方能力/工具 → 成熟 OSS → 最後才新增工具。安裝、登記、技能數、包裝或測試 PASS 不等於產品改善；只有實際套入產品、可見/可測改善、無明顯回歸且 Sol 接受才算落地。

## 驗證、證據、Git
- Build/lint/test PASS 只證明對應工程條件，不能冒充真人流程成功；歷史證據不能冒充本輪驗證。
- 驗證工具失敗與產品失敗分開；證據少而有效，不按代理角色複製大量報告/ZIP。
- 只修改當前 Issue 最小必要範圍；禁止 `git reset --hard`、`git clean -fd`、force push、改寫已發布歷史或刪除未知資料。
- 只有 P0/P1=0、scope drift=0、必要驗證完成且 Sol Gate 通過才可宣稱 PASS。

## (1）PERT/CPM圖
```mermaid
graph LR
    A[1. 研擬計畫 1d] --> B[2. 任務分配 4d]
    A --> C[3. 取得硬體 17d]
    B --> D[4. 程式開發 70d]
    C --> E[5. 安裝硬體 10d]
    D --> F[6. 程式測試 30d]
    E --> G[7. 撰寫使用手冊 25d]
    E --> H[8. 轉換檔案 20d]
    F --> I[9. 系統測試 25d]
    G --> J[10. 使用者訓練 20d]
    H --> J
    I --> K[11. 使用者測試 25d]
    J --> K

    %% 標記關鍵路徑
    linkStyle 0 stroke:red,stroke-width:3px;
    linkStyle 2 stroke:red,stroke-width:3px;
    linkStyle 4 stroke:red,stroke-width:3px;
    linkStyle 8 stroke:red,stroke-width:3px;
    linkStyle 10 stroke:red,stroke-width:3px;

    style A fill:#ffcccc,stroke:#ff0000,stroke-width:2px;
    style B fill:#ffcccc,stroke:#ff0000,stroke-width:2px;
    style D fill:#ffcccc,stroke:#ff0000,stroke-width:2px;
    style F fill:#ffcccc,stroke:#ff0000,stroke-width:2px;
    style I fill:#ffcccc,stroke:#ff0000,stroke-width:2px;
    style K fill:#ffcccc,stroke:#ff0000,stroke-width:2px;
```
---
## (2) 甘特圖
```mermaid
gantt
    title 專案甘特圖 (紅色 = 關鍵路徑，總工期 155 天)
    dateFormat  YYYY-MM-DD
    axisFormat  %m/%d

    section 計畫
    研擬計畫       :crit, a1, 2025-09-01, 1d
    任務分配       :crit, a2, after a1, 4d
    取得硬體       :a3, after a1, 17d

    section 開發
    程式開發       :crit, a4, after a2, 70d
    安裝硬體       :a5, after a3, 10d

    section 測試 & 文件
    程式測試       :crit, a6, after a4, 30d
    撰寫使用手冊   :a7, after a5, 25d
    轉換檔案       :a8, after a5, 20d

    section 系統驗證
    系統測試       :crit, a9, after a6, 25d
    使用者訓練     :a10, after a7, 20d
    使用者訓練     :a10, after a8, 20d
    使用者測試     :crit, a11, after a9, 25d
    使用者測試     :crit, a11, after a10, 25d


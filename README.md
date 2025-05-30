
flowchart TD
    subgraph PHASE1 ["🏢 GIAI ĐOẠN 1: THIẾT LẬP KPI (ĐẦU NĂM)"]
        A["🎯 Bắt đầu thiết lập KPI<br/>cho năm mới"] --> B["👤 NHÂN VIÊN<br/>📱 Tạo yêu cầu phê duyệt<br/>Power Apps"]
        B --> C["📧 Hệ thống gửi thông báo<br/>📬 Teams/Outlook"]
        C --> D["👔 QUẢN LÝ<br/>📨 Nhận thông báo<br/>Teams/Outlook"]
        D --> E["📝 QUẢN LÝ<br/>✏️ Cập nhật mục tiêu T1-T12<br/>📊 Chỉnh sửa KPI"]
        E --> F{"🤔 Quản lý<br/>quyết định?"}
        
        F -->|✅ APPROVE| G["🔒 KPI ĐƯỢC DUYỆT<br/>✨ Status: Approved<br/>🚫 Không thể chỉnh sửa"]
        F -->|❌ REJECT| H["❌ BỊ TỪ CHỐI<br/>💭 Status: Rejected<br/>🔄 Yêu cầu chỉnh sửa"]
        H -.-> B
    end
    
    subgraph PHASE2 ["📊 GIAI ĐOẠN 2: THEO DÕI HIỆU SUẤT (HÀNG THÁNG)"]
        G --> I["📈 Bắt đầu chu kỳ<br/>theo dõi hàng tháng"]
        I --> J["👤 NHÂN VIÊN<br/>📊 Nhập kết quả thực hiện<br/>Performance Tracking"]
        J --> K["📤 Gửi yêu cầu<br/>phê duyệt kết quả<br/>📬 Teams/Outlook"]
        K --> L["👔 QUẢN LÝ<br/>📨 Kiểm tra kết quả<br/>Teams/Outlook"]
        L --> M{"🤔 Kết quả<br/>có đạt yêu cầu?"}
        
        M -->|✅ APPROVE| N["✅ KẾT QUẢ ĐƯỢC DUYỆT<br/>🎉 Status: Approved<br/>📈 Hoàn thành chu kỳ"]
        M -->|❌ REJECT| O["❌ KẾT QUẢ BỊ TỪ CHỐI<br/>💭 Status: Rejected<br/>🔄 Yêu cầu nhập lại"]
        O -.-> J
    end
    
    subgraph PHASE3 ["📈 GIAI ĐOẠN 3: PHÂN TÍCH & BÁO CÁO"]
        N --> P["📊 POWER BI DASHBOARD<br/>📈 Xem báo cáo tổng hợp<br/>📋 Phân tích hiệu suất<br/>🎯 So sánh mục tiêu"]
        P --> Q["🔄 TIẾP TỤC CHU KỲ<br/>📅 Tháng tiếp theo"]
        Q -.-> I
    end
    
    %% Styling
    classDef startEnd fill:#e3f2fd,stroke:#1976d2,stroke-width:3px,color:#000
    classDef employee fill:#e8f5e8,stroke:#4caf50,stroke-width:2px,color:#000
    classDef manager fill:#fff3e0,stroke:#ff9800,stroke-width:2px,color:#000
    classDef decision fill:#f3e5f5,stroke:#9c27b0,stroke-width:2px,color:#000
    classDef approved fill:#c8e6c9,stroke:#4caf50,stroke-width:3px,color:#000
    classDef rejected fill:#ffcdd2,stroke:#f44336,stroke-width:3px,color:#000
    classDef system fill:#e1f5fe,stroke:#03a9f4,stroke-width:2px,color:#000
    classDef dashboard fill:#fff8e1,stroke:#ffc107,stroke-width:3px,color:#000
    
    class A,I,Q startEnd
    class B,J employee
    class D,E,L manager
    class F,M decision
    class G,N approved
    class H,O rejected
    class C,K system
    class P dashboard

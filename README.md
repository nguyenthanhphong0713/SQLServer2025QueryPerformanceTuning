# SQL Server 2025 Query Performance Tuning (Ấn bản thứ 7)
**Tác giả:** Grant Fritchey  
**Bản dịch tiếng Việt chuyên ngành Cơ sở dữ liệu & Lập trình Hệ thống**

---

## Mục Lục Toàn Bộ 23 Chương

1. **[Chương 1: Tinh chỉnh Hiệu năng Truy vấn (Query Performance Tuning)](./Chuong_01_Query_Performance_Tuning.md)**
   - Quy trình tinh chỉnh lặp lại, thu thập đường cơ sở (Baseline), chỉ số hiệu năng và giới thiệu các tính năng mới trên SQL Server 2025.
2. **[Chương 2: Quá trình Sinh Kế hoạch Thực thi và Bộ Tối ưu hóa Truy vấn (Execution Plan Generation and the Query Optimizer)](./Chuong_02_Execution_Plan_Generation_and_the_Query_Optimizer.md)**
   - Kiến trúc Query Optimizer, Algebrizer, ước lượng chi phí, các pha tối ưu hóa (Trivial Plan, Search 0/1/2) và bộ đệm kế hoạch.
3. **[Chương 3: Các Phương pháp Thu thập Chỉ số Hiệu năng Truy vấn (Methods for Capturing Query Performance Metrics)](./Chuong_03_Methods_for_Capturing_Query_Performance_Metrics.md)**
   - Extended Events, Dynamic Management Views (DMVs), Query Store và cách thiết lập phiên giám sát.
4. **[Chương 4: Phân tích Hành vi Truy vấn Sử dụng Kế hoạch Thực thi (Analyzing Query Behavior Using Execution Plans)](./Chuong_04_Analyzing_Query_Behavior_Using_Execution_Plans.md)**
   - Cách đọc hiểu Estimated Plan và Actual Plan, các toán tử vật lý/logic, luồng dữ liệu và thuộc tính chi tiết trong kế hoạch XML.
5. **[Chương 5: Thống kê, Phân phối Dữ liệu và Ước lượng Số dòng (Statistics, Data Distribution, and Cardinality)](./Chuong_05_Statistics_Data_Distribution_and_Cardinality.md)**
   - Cấu trúc Histogram, Density Vector, mô hình Cardinality Estimator (CE), bảo trì thống kê tự động và thủ công.
6. **[Chương 6: Sử dụng Query Store cho Hiệu năng Truy vấn và Kế hoạch Thực thi (Using the Query Store for Query Performance and Execution Plans)](./Chuong_06_Using_the_Query_Store_for_Query_Performance_and_Execution_Plans.md)**
   - Kiến trúc Query Store, phát hiện suy thoái kế hoạch (Plan Regression), ép kế hoạch (Plan Forcing) và Query Store cho bản sao đọc.
7. **[Chương 7: Hành vi Bộ đệm Kế hoạch Thực thi (Execution Plan Cache Behavior)](./Chuong_07_Execution_Plan_Cache_Behavior.md)**
   - Cơ chế lưu trữ và tái sử dụng kế hoạch, Ad hoc workloads, Parameterization (Simple & Forced), Plan Cache Bloat.
8. **[Chương 8: Biên dịch lại Truy vấn (Query Recompilation)](./Chuong_08_Query_Recompilation.md)**
   - Nguyên nhân gây biên dịch lại (Schema changes, Statistics updates), Statement-level recompile, RECOMPILE hints.
9. **[Chương 9: Kiến trúc Chỉ mục (Index Architecture)](./Chuong_09_Index_Architecture.md)**
   - Cấu trúc B-Tree (Clustered & Nonclustered Indexes), Columnstore Indexes, Filtered Indexes, XML/JSON/Vector Indexes.
10. **[Chương 10: Hành vi của Chỉ mục (Index Behaviors)](./Chuong_10_Index_Behaviors.md)**
    - Seek vs. Scan, Covering Indexes (INCLUDE), thứ tự cột khóa, SARGability và chiến lược thiết kế chỉ mục.
11. **[Chương 11: Tra cứu Khóa và Các Giải pháp (Key Lookups and Solutions)](./Chuong_11_Key_Lookups_and_Solutions.md)**
    - Phân tích chi phí Key Lookup / RID Lookup và cách giải quyết bằng Covering Index hoặc Clustered Index.
12. **[Chương 12: Xử lý Phân mảnh Chỉ mục (Dealing with Index Fragmentation)](./Chuong_12_Dealing_with_Index_Fragmentation.md)**
    - Phân mảnh nội bộ và phân mảnh bên ngoài, Page Splits, Fill Factor, REORGANIZE vs. REBUILD.
13. **[Chương 13: Truy vấn Nhạy cảm với Tham số: Nguyên nhân và Giải pháp (Parameter-Sensitive Queries: Causes and Solutions)](./Chuong_13_Parameter_Sensitive_Queries_Causes_and_Solutions.md)**
    - Parameter Sniffing, biến cục bộ, OPTIMIZE FOR, Parameter Sensitive Plan (PSP) Optimization trong SQL Server 2022/2025.
14. **[Chương 14: Phân tích Thiết kế Truy vấn (Query Design Analysis)](./Chuong_14_Query_Design_Analysis.md)**
    - Cấu trúc câu lệnh T-SQL, hàm trên cột lọc, kiểu dữ liệu, chuyển đổi ngầm định, Subqueries, CTE và Window Functions.
15. **[Chương 15: Giảm thiểu Sử dụng Tài nguyên Truy vấn (Reduce Query Resource Use)](./Chuong_15_Reduce_Query_Resource_Use.md)**
    - Giảm thiểu I/O, CPU và Memory Grant, chia nhỏ thao tác DML lớn, quản lý TempDB (Bảng tạm vs. Biến bảng).
16. **[Chương 16: Chặn và Các Tiến trình Bị Chặn (Blocking and Blocked Processes)](./Chuong_16_Blocking_and_Blocked_Processes.md)**
    - Kiến trúc Khóa (Locking), các mức độ cô lập giao dịch (Isolation Levels), RCSI, Snapshot Isolation và **Optimized Locking (TID Locking & Lock After Qualification - LAQ) trên SQL Server 2025**.
17. **[Chương 17: Nguyên nhân và Giải pháp cho Khóa chết (Causes and Solutions for Deadlocks)](./Chuong_17_Causes_and_Solutions_for_Deadlocks.md)**
    - Cơ chế Deadlock, Deadlock Priority, thu thập và phân tích Deadlock Graph, xử lý lỗi 1205 và phòng ngừa khóa chết.
18. **[Chương 18: Xử lý Từng dòng từ Con trỏ và Các Nguyên nhân Khác (Row-by-Row Processing from Cursors and Other Causes)](./Chuong_18_Row_by_Row_Processing_from_Cursors_and_Other_Causes.md)**
    - RBAR (Row By Agonizing Row), phân loại Cursor (Location, Concurrency, Type), Default Result Set, MARS và chuyển đổi sang truy vấn tập hợp (Set-based).
19. **[Chương 19: Bảng và Thủ tục Lưu trữ OLTP Tối ưu hóa Bộ nhớ (Memory-Optimized OLTP Tables and Procedures)](./Chuong_19_Memory_Optimized_OLTP_Tables_and_Procedures.md)**
    - Kiến trúc In-Memory OLTP (Hekaton), Hash Indexes vs. Nonclustered Bw-Tree Indexes, Natively Compiled Stored Procedures.
20. **[Chương 20: Cơ sở Dữ liệu Đồ thị (Graph Databases)](./Chuong_20_Graph_Databases.md)**
    - Bảng Nút (Node Tables) và Bảng Cạnh (Edge Tables), mệnh đề `MATCH`, hàm `SHORTEST_PATH` và tối ưu hóa chỉ mục đồ thị.
21. **[Chương 21: Xử lý Truy vấn Thông minh (Intelligent Query Processing)](./Chuong_21_Intelligent_Query_Processing.md)**
    - Interleaved Execution, Memory Grant Feedback (Percentile & Persistence), Cardinality Estimation (CE) Feedback, Degree of Parallelism (DOP) Feedback, Approximate Query Processing, Table Variable Deferred Compilation, Scalar UDF Inlining.
22. **[Chương 22: Tự động Tinh chỉnh trong Azure và SQL Server (Automated Tuning in Azure and SQL Server)](./Chuong_22_Automated_Tuning_in_Azure_and_SQL_Server.md)**
    - Automatic Plan Correction (`FORCE_LAST_GOOD_PLAN`), `sys.dm_db_tuning_recommendations`, Automatic Index Management trên Azure SQL.
23. **[Chương 23: Phương pháp luận Tinh chỉnh Truy vấn (A Query Tuning Methodology)](./Chuong_23_A_Query_Tuning_Methodology.md)**
    - Danh mục kiểm tra (Checklist) toàn diện về Thiết kế Cơ sở dữ liệu, Thiết lập Cấu hình, Quản trị Hệ thống và Thiết kế Truy vấn.

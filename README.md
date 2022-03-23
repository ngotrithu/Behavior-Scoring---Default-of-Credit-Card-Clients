# Behavior-Scoring-Default-of-Credit-Card-Clients
## Mô tả:
- Bộ dữ liệu này chứa thông tin về các khoản thanh toán mặc định, các yếu tố nhân khẩu học, dữ liệu tín dụng, lịch sử thanh toán và bảng sao kê hóa đơn của các khách hàng sử dụng thẻ tín dụng ở Đài Loan từ tháng 4 năm 2005 đến tháng 9 năm 2005
## Mục đích:
- Dự báo xác suất vỡ nợ của KH hay dự báo liệu KH có mất khả năng thanh toán trong kỳ hạn sắp tới hay không?
## Techniques:
- Exploratory Data Analysis (EDA)
- Feature Engineering
- Feature Selection: RFE, RFECV, RF Importance, PCA
- Feature Scaling
- SMOTE
- Build Models
- Model Selection
- Advanced GridSearchCV Techniques
## Modeling:
- Logistic Regression
- Decision Tree
- Random Forest
- AdaBoost
- CatBoost
- LightGBM
- XGB
- Voting Classifier + Non-Correlation Models
- Stacking Classifier
## Fine Tune Hyperparameters with `GridSearchCV`
- Sử dụng `early_stopping_rounds` để tìm ra `n_estimators` phù hợp cho bài toán
- Sử dụng các kỹ thuật GridSearch nâng cao nhằm tận dụng tối đa sức mạnh các hyperparameters của mô hình XGBoost
- Kết thúc quá trình GridSearchCV mô hình đã được cải thiện độ chính xác từ 81.5% lên 82.197% (tăng gần 7 điểm phần trăm)

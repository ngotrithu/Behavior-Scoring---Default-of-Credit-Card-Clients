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

## Kết luận
- Với bài toán Behavior Scoring, chúng ta nên chú trọng vào việc giảm số lượng sai lầm loại II (FN) mà mô hình phán đoán được. Những khách hàng thuộc sai lầm loại II về thực tế họ đã chưa thanh toán nhưng mô hình dự đoán những khách hàng này đã thanh toán theo đúng kỳ hạn. Xét theo góc độ tín dụng, nếu KH trả lãi không đủ và đúng hạn thì điểm tín dụng của KH sẽ thấp, nhảy nhóm nợ trên hệ thống tin tín dụng quốc gia CIC, điều này sẽ gây khó khăn cho các khoản vay tiếp theo của KH vì để có một CIC đẹp là người đã từng vay và trả lãi đúng hạn nên sai lầm loại II (FN) có tính chất nghiêm trọng hơn.
- Do đó,  ngoài việc lựa chọn mô hình tốt, chúng ta cũng cần lựa chọn những mô hình có các TH thuộc sai lầm loại II là thấp nhất.
- Dựa vào đồ thị trên kết hợp với confusion matrix của các mô hình đã huấn luyện ở trên thì hiệu suất của mô hình XGB với `booster = gbtree` cho độ chính xác tốt nhất 82.197%%  và không cần không quá nhiều thời gian để huấn luyện mô hình và có số lượng sai lầm loại II thấp nhất (355), nên chúng ta sẽ chọn mô hình này làm mô hình cuối cùng để áp dụng vào bài toán này!

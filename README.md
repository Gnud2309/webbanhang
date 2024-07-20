*Phần phía front-end:
- Bạn hãy install thư viện yarn trên terminal về sau đó hãy cd vào thư mục front-end chạy lệnh yarn install
- Sau đó hãy chạy lệnh npm start để chạy angular trên cổng 4200

*Phía Back-end:
- Nếu chỉ cần demo thì hãy chuyển cổng của mysql về cổng 3307 hoặc hãy chỉnh lại port trong file application.yml về cổng mặc định 3306 khi ấy sẽ chạy được
- Tuy nhiên trong source này của tôi còn có build redis,kafka và docker nếu bạn muốn chạy trên docker thì hãy làm như sau:
  + đầu tiên hãy vào file deployment và build docker mysql với lệnh này:
    docker-compose -f ./deployment.yaml up -d mysql8-container
  + build phpmyadmin với lệnh này:
    docker-compose -f ./deployment.yaml up -d phpmyadmin8-container
  + sau khi xong được 2 cái kia thì sẽ chạy khởi tạo container redis với lệnh sau:
    docker-compose -f ./deployment.yaml up -d redis-container
  + trong file deployment tôi đã setup sẵn các docker-compose bạn chỉ việc dùng lệnh và mở terminal cd tới thư mục chứ tổng của shopapp giống như trên git của tôi
    và chạy các lệnh trên những hướng dẫn trên yêu cầu bạn có biết về docker và hiểu những chỗ tui chưa chỉ để setup
  + tiếp theo là chạy kafka thì giống như trên và lệnh tôi đã viết sãn comment sãn trong file kafka-deployment rồi.

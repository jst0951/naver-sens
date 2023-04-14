# naver-sens
Naver Cloud Platform SENS(Simple &amp; Easy Notification Service) python wrapper

Install : 
```
pip install naver-sens
```

Usage Guide : https://codedbyjst.tistory.com/10

send message ex.
```python3
from naver_sens import SensClient

sens_client = SensClient(
  service_id="ncp:sms:kr:298829194091:testproject", 
  access_key="mEFm77AiXuBFUfM0g9EI", 
  secret_key="JKo84GDVewLYYO8ALZqSc7j73kTziDEqy2NRSf6p")

resp = sens_client.send_message(
    from_num="01012345678",
    to_num="01087654321",
    content="안녕하세요, naver-sens 테스트입니다!"
  )
print(resp.content)
```

send message at reserveTime ex.
```python3
resp = sens_client.send_message(
    from_num="01012345678",
    to_num="01087654321",
    content="안녕하세요, naver-sens 시간 예약 테스트입니다!",
    reserveTime="2023-04-14 16:20"
  )
print(resp.content)
```

send message with image ex.
```python3
resp = sens_client.send_message_with_image(
    from_num="01012345678", 
    to_num="01087654321", 
    content="이미지와 같이 보내진 메세지입니다!",
    img_dir="./image.jpg")
print(resp.content)
```


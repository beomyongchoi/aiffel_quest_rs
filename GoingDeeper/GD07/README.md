# AIFFEL Campus Online Code Peer Review Templete
- 코더 : 최범용
- 리뷰어 : 원균재


# PRT(Peer Review Template)
- [X]  **1. 주어진 문제를 해결하는 완성된 코드가 제출되었나요?**
    - 문제에서 요구하는 최종 결과물이 첨부되었는지 확인
    - <img width="490" height="436" alt="image" src="https://github.com/user-attachments/assets/f34e99db-2190-4261-b68a-4e66083bc8fa" />
<img width="1148" height="412" alt="image" src="https://github.com/user-attachments/assets/a39c460e-11eb-4cb8-9a89-2183fd896e3e" />
시각화, loss값의 수렴이 잘 나타났다.
    
- [X]  **2. 전체 코드에서 가장 핵심적이거나 가장 복잡하고 이해하기 어려운 부분에 작성된 
주석 또는 doc string을 보고 해당 코드가 잘 이해되었나요?**
    - 해당 코드 블럭을 왜 핵심적이라고 생각하는지 확인
    - 해당 코드 블럭에 doc string/annotation이 달려 있는지 확인
    - 해당 코드의 기능, 존재 이유, 작동 원리 등을 기술했는지 확인
    - 주석을 보고 코드 이해가 잘 되었는지 확인
<img width="752" height="350" alt="image" src="https://github.com/user-attachments/assets/feca061a-b1c0-4bcc-a23a-1bfb15bfe4d1" />

- [X]  **3. 에러가 난 부분을 디버깅하여 문제를 해결한 기록을 남겼거나
새로운 시도 또는 추가 실험을 수행해봤나요?**
    - 문제 원인 및 해결 과정을 잘 기록하였는지 확인
    - 프로젝트 평가 기준에 더해 추가적으로 수행한 나만의 시도, 실험이 기록되어 있는지 확인
    <img width="1289" height="504" alt="image" src="https://github.com/user-attachments/assets/09a661d3-246e-4cc6-bf6f-f724aae54745" />
모델의 파라미터 수는 모델의 크기를 결정짓는 요소다. 이 노트북에서는 최적의 lr을 실험을 통해 구한 다음 파라미터 수를 1.4M에 두고 모델의 레이어, 차원 수를 조정하면서 실험하였다.
        
- [X]  **4. 회고를 잘 작성했나요?**
    - 주어진 문제를 해결하는 완성된 코드 내지 프로젝트 결과물에 대해
    배운점과 아쉬운점, 느낀점 등이 기록되어 있는지 확인
<img width="1326" height="687" alt="image" src="https://github.com/user-attachments/assets/df64189e-1f15-4393-bd75-b059e0851de6" />


- [X]  **5. 코드가 간결하고 효율적인가요?**
    - 파이썬 스타일 가이드 (PEP8) 를 준수하였는지 확인
    - 코드 중복을 최소화하고 범용적으로 사용할 수 있도록 함수화/모듈화했는지 확인
<img width="753" height="614" alt="image" src="https://github.com/user-attachments/assets/06d8b5eb-ebf9-49c7-b24f-bd71c5de72ef" />
앞에서 정의한 임베딩, 인코더, 드롭아웃, 어텐션 을 BERT 클래스 안에 넣어 가독성이 좋았다.

# 회고(참고 링크 및 코드 개선)
```
# 리뷰어의 회고를 작성합니다.
# 코드 리뷰 시 참고한 링크가 있다면 링크와 간략한 설명을 첨부합니다.
# 코드 리뷰를 통해 개선한 코드가 있다면 코드와 간략한 설명을 첨부합니다.
```
모델의 파라미터를 1M으로 한정하여 진행하여 과적합을 막은 점이 인상적이었다. 사용하는 데이터 양에 적합하게 모델 형태를 반족하듯이 변경하였는데, '깊고 좁은' 모델과 '얕고 넓은' 모델으로 실험을 시작한 것이 인상적이었다. 개인적으로 보고서를 굉장히 잘 쓰신다, 실험을 많이 진행하셨는데 시간을 많이 쓰신 티가 나는 보고서와 코드였다.

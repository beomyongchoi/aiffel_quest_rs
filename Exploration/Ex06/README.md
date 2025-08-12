# AIFFEL Campus Online Code Peer Review Templete
- 코더 : 최범용
- 리뷰어 : 박범찬


# PRT(Peer Review Template)
- [x]  **1. 주어진 문제를 해결하는 완성된 코드가 제출되었나요?**
    - 문제에서 요구하는 최종 결과물이 첨부되었는지 확인
        - 중요! 해당 조건을 만족하는 부분을 캡쳐해 근거로 첨부
          <img width="578" height="367" alt="image" src="https://github.com/user-attachments/assets/bf737dad-d68a-4cd1-9ebb-d9d5e0ab4c46" />
          -seq2seq 모델 활용

          
    
- [x]  **2. 전체 코드에서 가장 핵심적이거나 가장 복잡하고 이해하기 어려운 부분에 작성된 
주석 또는 doc string을 보고 해당 코드가 잘 이해되었나요?**
    - 해당 코드 블럭을 왜 핵심적이라고 생각하는지 확인
    - 해당 코드 블럭에 doc string/annotation이 달려 있는지 확인
    - 해당 코드의 기능, 존재 이유, 작동 원리 등을 기술했는지 확인
    - 주석을 보고 코드 이해가 잘 되었는지 확인
        - 중요! 잘 작성되었다고 생각되는 부분을 캡쳐해 근거로 첨부
          <img width="743" height="559" alt="image" src="https://github.com/user-attachments/assets/e59db5b1-2e49-4c2b-9e0f-f541a7225ac6" />
          - 인코더, 어텐션 과정에서 주석을 자세히 기록

          
        
- [x]  **3. 에러가 난 부분을 디버깅하여 문제를 해결한 기록을 남겼거나
새로운 시도 또는 추가 실험을 수행해봤나요?**
    - 문제 원인 및 해결 과정을 잘 기록하였는지 확인
    - 프로젝트 평가 기준에 더해 추가적으로 수행한 나만의 시도, 
    실험이 기록되어 있는지 확인
        - 중요! 잘 작성되었다고 생각되는 부분을 캡쳐해 근거로 첨부
          <img width="577" height="595" alt="image" src="https://github.com/user-attachments/assets/7da8763d-bbbf-46ac-9103-c1d52e869c1d" />
          - epoch을 50에서 30으로 변경한 후, 17에서 early stop을 활용


        
- [x]  **4. 회고를 잘 작성했나요?**
    - 주어진 문제를 해결하는 완성된 코드 내지 프로젝트 결과물에 대해
    배운점과 아쉬운점, 느낀점 등이 기록되어 있는지 확인
    - 전체 코드 실행 플로우를 그래프로 그려서 이해를 돕고 있는지 확인
        - 중요! 잘 작성되었다고 생각되는 부분을 캡쳐해 근거로 첨부
          <img width="729" height="246" alt="image" src="https://github.com/user-attachments/assets/f9db2891-ad83-4388-8ddd-9a58419f7d81" />
          - 실행 결과에 대한 회고를 정리

        
- [x]  **5. 코드가 간결하고 효율적인가요?**
    - 파이썬 스타일 가이드 (PEP8) 를 준수하였는지 확인
    - 코드 중복을 최소화하고 범용적으로 사용할 수 있도록 함수화/모듈화했는지 확인
        - 중요! 잘 작성되었다고 생각되는 부분을 캡쳐해 근거로 첨부
          <img width="620" height="637" alt="image" src="https://github.com/user-attachments/assets/ad269fe4-a60f-44dc-9377-24d2790eb9c3" />
          - 가장 성능이 좋은 모델을 불러와 요약 후 결과를 출력



# 회고(참고 링크 및 코드 개선)

-분석단계, 정제단계, 정규화와 불용어 제거, 데이터셋 분리, 인코딩 과정이 빠짐없이 체계적으로 진행됨
-모델 학습이 진행되면서 train loss와 validation loss가 감소하는 경향을 그래프를 통해 확인
-실제 요약문에 있는 핵심 단어들이 요약 문장 안에 포함되었다.
-두 요약 결과를 문법완성도 측면과 핵심단어 포함 측면으로 나누어 비교하고 분석함

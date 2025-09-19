# AIFFEL Campus Online Code Peer Review Templete
- 코더 : 최범용
- 리뷰어 : 원균재


# PRT(Peer Review Template)
- [X]  **1. 주어진 문제를 해결하는 완성된 코드가 제출되었나요?**
    - 문제에서 요구하는 최종 결과물이 첨부되었는지 확인
    <img width="849" height="654" alt="image" src="https://github.com/user-attachments/assets/044196e9-268f-4210-933e-473c7deccfbd" />

- [X]  **2. 전체 코드에서 가장 핵심적이거나 가장 복잡하고 이해하기 어려운 부분에 작성된 
주석 또는 doc string을 보고 해당 코드가 잘 이해되었나요?**
    - 해당 코드 블럭을 왜 핵심적이라고 생각하는지 확인
    - 해당 코드 블럭에 doc string/annotation이 달려 있는지 확인
    - 해당 코드의 기능, 존재 이유, 작동 원리 등을 기술했는지 확인
    - 주석을 보고 코드 이해가 잘 되었는지 확인
<img width="810" height="96" alt="image" src="https://github.com/user-attachments/assets/f2c966cc-512d-45b8-9720-f4cd1fa3edb7" />
<img width="821" height="132" alt="image" src="https://github.com/user-attachments/assets/fdae927b-c89d-4e23-88f1-49c81dcfe5dd" />
<img width="821" height="236" alt="image" src="https://github.com/user-attachments/assets/6df7e3ab-b256-4c10-8b2d-839af93bb6e6" />
주석을 읽고 코드를 이해하기 좋았다.


- [X]  **3. 에러가 난 부분을 디버깅하여 문제를 해결한 기록을 남겼거나
새로운 시도 또는 추가 실험을 수행해봤나요?**
    - 문제 원인 및 해결 과정을 잘 기록하였는지 확인
    - 프로젝트 평가 기준에 더해 추가적으로 수행한 나만의 시도, 실험이 기록되어 있는지 확인

 <img width="823" height="657" alt="image" src="https://github.com/user-attachments/assets/7a6519ef-8c73-449d-9f36-9ee5e1e59d10" />
   전체 파라미터를 모두 학습하는 대신, LoRA를 SFT와 RM 모델에 적용하여 훨씬 적은 수의 파라미터만으로 효율적인 튜닝을 진행했
        
- [X]  **4. 회고를 잘 작성했나요?**
    - 주어진 문제를 해결하는 완성된 코드 내지 프로젝트 결과물에 대해
    배운점과 아쉬운점, 느낀점 등이 기록되어 있는지 확인
<img width="841" height="352" alt="image" src="https://github.com/user-attachments/assets/090a986f-0cd4-4b9d-b049-0f3f51a23c89" />

- [X]  **5. 코드가 간결하고 효율적인가요?**
    - 파이썬 스타일 가이드 (PEP8) 를 준수하였는지 확인
    - 코드 중복을 최소화하고 범용적으로 사용할 수 있도록 함수화/모듈화했는지 확인

<img width="830" height="323" alt="image" src="https://github.com/user-attachments/assets/77feeeb2-153e-4e61-9993-4c9c95651876" />

# 회고(참고 링크 및 코드 개선)
```
# 리뷰어의 회고를 작성합니다.
# 코드 리뷰 시 참고한 링크가 있다면 링크와 간략한 설명을 첨부합니다.
# 코드 리뷰를 통해 개선한 코드가 있다면 코드와 간략한 설명을 첨부합니다.
```
RLHF를 성공적으로 구현하였고, 특히 데이터 분석 및 정제부터 SFT, RM, PPO 각 단계의 모델을 하나의 파이프라인으로 구축하고, LoRA를 적용한 점이 인상적이었다

한 가지 개선 아이디어가 있다면, 최종 성능 평가 부분에서 세 모델(Baseline, SFT, PPO)의 답변을 생성하는 코드가 각각 반복되는 경향이 있었는데, 이 부분을 아래와 같이 하나의 함수로 추상화하면 코드가 더 간결해질것 같습니다! 고잉디퍼 마지막까지 정말 수고하셨습니다!
```
범용님 리뷰만 이번 기간에 여러번 한것 같은데 볼 때 마다 영감이 되는 실험들과 정리 능력을 보여주셨습니다. 많은 공부가 된 것같아 감사합니다~
```

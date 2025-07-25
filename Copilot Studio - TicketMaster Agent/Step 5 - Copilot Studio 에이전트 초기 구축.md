

# Step 5 – Copilot Studio 에이전트 초기 구축

> **목표:** Copilot Studio에서 에이전트(agent)를 만들고, 우리가 만든 \*\*사용자 지정 커넥터(custom connector)\*\*만 사용하도록 초기 설정을 완료합니다. 

---

## 1. Copilot Studio로 이동 및 새 에이전트 만들기

1. **Copilot Studio** 환경으로 이동합니다.

   * 반드시 사용자 지정 커넥터를 만든 **동일한 Power Platform 환경**(예: `copilot workshop12`)인지 확인하세요.
2. **New agent(새 에이전트 만들기)** 클릭 → 에이전트 생성 시작

![새 에이전트 만들기](https://github.com/user-attachments/assets/505e0623-95f4-489b-9f8e-bbd0fbd0bd20)

---

## 2. 에이전트 기본 정보 설정

1. **에이전트 이름**: 예) `Events Agent`
2. **초기 지침(Instruction)**: 에이전트가 수행할 작업을 명확히 적습니다.

   * 예: “이 에이전트는 사용자 지정 커넥터를 사용하여 예정된 이벤트에 대한 세부 정보를 가져옵니다.”
3. **만들기(생성)** 버튼 클릭

> 지침은 대화로 입력하지 않고 **구성으로 건너뛰기** 후, 명시적으로 입력해도 됩니다.

![에이전트 이름/지침 설정](https://github.com/user-attachments/assets/c1e67486-ff35-4578-98c2-0ccc7a445353)

4. 생성형 오케스트레이션
   * 에이전트가 언어 모델을 사용하여 사용자 요청을 해석하고, 정의된 도구를 지능적으로 조작할 수 있도록 오케스트레이션을 **사용**으로 설정합니다.
      지침 예시:
      - 사용자 지정 커넥터를 사용하여 예정된 이벤트에 대한 세부 정보를 가져옴
      - 사용자에게 이벤트 세부 정보를 제공하고 필요한 정보를 검색함
      - 사용자 요청에 따라 이벤트 정보를 업데이트하고 관리함
      - 이벤트 관련 질문에 대한 답변을 제공함
      - 사용자에게 친절하고 명확하게 안내함
      - 사용자가 한국어로 얘기하면, 그걸 영어로 번역해서 거기서 input parameter를 식별해서 도구를 불러올 때 사용함
      예시) 비엔나는 Vienna"
![생성형 오케스트레이션](https://github.com/user-attachments/assets/3ac8edf8-0d6e-48d6-bd8e-a0410f00a611)




---

## 3. 에이전트 세부 설정: 일반 지식 비활성화

1. 상단의 **설정(Setting)** 메뉴로 이동합니다.

![설정 메뉴 진입](https://github.com/user-attachments/assets/43f74733-73b0-4b00-b637-b0358966fd87)

2. **생성형 AI 설정**에서 **일반 참조 자료 사용(General knowledge)** 옵션을 \*\*끄기(Off)\*\*로 변경 후 저장합니다.

   * 이렇게 하면 에이전트는 일반 웹 지식이나 오래된 정보(예: 2023년 Oasis 정보) 대신, **오직 사용자 지정 커넥터**를 통해 실시간 데이터를 조회합니다.

![일반 참조 자료 사용 끄기](https://github.com/user-attachments/assets/5d89be62-fa61-42f8-a230-e35e7a641f5e)

---

> 이제 Copilot Studio 에이전트가 준비되었습니다. 다음 단계에서 이 에이전트에 **‘이벤트 가져오기(GetEvents)’ 작업**을 연결해 실제로 대화 중 이벤트 정보를 조회할 수 있도록 구성하세요.

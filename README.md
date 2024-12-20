## 개요
- NomadCoder의 full stack gpt 강의 내용 정리
- [강의링크](https://nomadcoders.co/fullstack-gpt/lectures/4540)

### 기본개념
- LLM : 대규모 언어 모델로 인간처럼 자연어 기반 텍스트를 이해하고 생성할 수 있는 모델
- OpenAI : LLM 개발 회사 중 GPT를 개발한 곳 
- LangChain : 파이썬 라이프러리 - LLM을 효과적으로 활용할 수 있음
    - LLM을 다른 서비스 API, DB와 연결할 수 있도록 지원

## 강의 소개
- 목적 : GPT-4, Langchain 을 활용하여 실전형 AI 웹 서비스 7가지 구현
  - 본인이 가진 데이터를 이용해서 GPT 어플리케이션을 만들기
- 활용하는 패키지
  - Langchain, GPT-4, Whisper, FastAPI, Streamlit, Pinecone, Hugging Face
- 구현하는 AI 웹서비스(6종)
  -  DocumentGPT, PrivateGPT, QuizGPT, SiteGPT, MeetingGPT, InvestorGPT
- 구현하는 ChatGPT 플러그인 (1종)
  - ChefGPT

## 사용 도구
- langchain 활용
    - 랭체인 사용없이 open AI ApI 활용해서 GPT4를 사용하는 것과 비교
    - 랭체인을 사용하면 6가지 종류의 memory를 얻을 수 있으나 gpt는 제공하지 않음
    - 연결해서 작동하는 방식
    - 프롬프트, 모듈 등을 위한 LLM이 있음
    - 나의 코드를 모두 작성할 필요없음
    - LLM 어플리케이션을 만들기 위한 모든 모듈간의 호환을 담당해줄 것 
- claude 
    - 한줄의 코드만 수정
    특정 모델을 AI와 결합하는 대신 랜체인을 사용
- langsmith 
    - llm 어플리케이션을 위한 에이전트
    - 코드 호출 횟수 등 
- streamit 
    - 모든 종류의 AI 어플리케이션을 위한 
- pinecone
    - 벡터를 위한 데이터베이스 
    - 계정 생성 필요
- hugging face
    - gpt4가 아닌 다른 모델을 가져오는 방법 
    - 최소한 어떤 것인지, 어떻게 쓸수있는지 배우기
    - gpt4보단 낮겠지만 비교해보는 용도로 다른 모델 써보기
- FastAPI

# 사전준비
### chatGPT 유료 결제 필요
- gpt4 필요함
- plugin store 사용 필요

## platform.openapi.com 계정 생성 필요
- api key 생성 - 카드등록해서 사용한 것만 비용 지급됨
- 비용 발생함
### Usage limit 설정***필수
- hard limit : 상한선 설정해주기
- soft limit : 알람정도

## 내용
- 기술개발이 너무 빨라짐
- 강의를 보면서도 계속 새로운 chain이 생겨남
- 새로운 agent 등이 생김
- 우리환경에서 설치하려고 할때 해야하는 것을 이해해야해
- 랭체인문서를 살펴보고 커스텀할수있어야함


# 가상환경 만들기 
## 가상환경 폴더 생성
- 현재 위치에 가상환경 만들기 
  - `python -m venv ./env`
  - 설치할 모든 패키지가 들어있음
- gitignore에 env 추가
  - `env/`
- 가상환경 활성화 
  - [pytohn-venv docs](https://docs.python.org/ko/3.13/library/venv.html#creating-virtual-environments)
  - windows
    - cmd.exe
      - `env\Scripts\activate` 
    - PowerShell
      - `env\Scripts\Activate.ps1`

# LangChain 
## Modules
> 해당 자료 참고 링크 : [langchain v0.1 기준 Docs 페이지링크 : 현재 유지보수 지원하지 않는 버전](https://python.langchain.com/v0.1/docs/modules/)
- LangChain에는 다양한 모듈이 존재()
    - Model IO
        - prompt
        - chat models
        - llms
    - Retravel : 외부데이터로 접근하여 어떻게 모델에 제공할 것인지 / 데이터들로 작업하게 하고 모델에게 제공할 수 있는지에 대한 이야기 
        - Document loaders
        - Text splitters
        - Embedding models
        - Vector stores
        - Retrievers
        - Indexing
    - Composition
        - Tools
        - Agents : AI가 독립적으로 작동할 수 있게 해주는 기능
            - 예를 들어, Chains이 필요한 도구를 선택하여 사용할 수 있도록 하거나, 
            - 일을 chain에게 시키고 그에 맞는 커스텀 도구를 만들어, chains가 스스로 일하게 함 
        - Chains
    - Memory
        - 챗봇에 메모리하게 하는 것
    - Callbacks
        - 모델이 하고있는 작업을 알 수 있도록 하는것 . 마지막이 아니라 중간에 알게하는 것
        - 모델이 답변을 제공하기 전에 실제로 모델이 하고 있는 작업/생각에 대한 중간 단계를 알 수 있게




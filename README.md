# [카피 - 웹 프론트엔드 - 나무위키] 허브위키 v0.1

## 실행 하기
git bash에서

```bash
git clone https://github.com/cw7430/hub-wiki-front.git
cd hub-wiki-front
npm run dev
```
## 프로젝트 목적
- 이 프로젝트는 Nuxt 3 기반으로 구현한 나무위키 스타일의 위키 시스템이다
- 정적 위키와 달리 SSR 기반으로 최신 문서 조회와 버전 히스토리를 제공한다

## 요구사항
- 누구나 새로운 위키 문서를 생성할 수 있다
- 누구나 모든 위키 문서를 열람할 수 있다
- 생성된 위키 문서는 수정, 삭제할 수 없다

## 기술 스택
- Frontend: Nuxt 4, Vue 3, TypeScript
- SSR: Nitro, Vite
- Language: Vue SFC, Composition API

## 프로젝트 구조
```bash
└── src/
    ├── app/
    │   └── app.vue
    ├── pages/
    │   ├── edit/
    │   ├── history/
    │   └── w/
    ├── layouts/
    ├── processes/
    ├── widgets/
    ├── features/
    ├── entities/
    └── shared/
```

## 페이지
- / : 메인 페이지
- /w/[문서이름] : 문서의 최근 버전 보기
- /w/[문서이름]?version=[버전] : 문서의 특정 버전 보기
- /edit/[문서이름] : 새로운 문서 생성하기
- /history/[문서이름] : 문서의 모든 버전 보기

## API
- 공통
  - 문서 제목으로 문서 찾기
    - Query wiki_doc_pk
- /w/[문서이름]
  - 해당 문서의 최신 버전 읽기
    - Query wiki_doc_pk
- /edit/[문서이름]
  - 해당 문서의 최신 버전 읽기
    - Query wiki_doc_pk
  - 새로운 문서 생성하기
    - Mutation insert_wiki_doc
  - 문서의 새로운 버전 생성하기
    - Mutation insert_doc_version
- /history[문서이름]
  - 해당 문서의 모든 버전 읽기
    - Query wiki_doc_pk

## 테스트
### 문서 검색
- 검색 창에 문서 이름을 입력한다
  - 문서가 있는 경우 최신 버전의 문서를 표시한다
  - 문서가 없는 경우 새 문서 작성 링크를 표시한다
### 새 문서 작성
  - 새로운 문서를 작성 완료 하면 해당 문서 페이지로 이동한다
### 기존 문서 편집
  - 기존 문서를 편집하면 해당 문서 페이지가 편집한 문서로 대체된다
  - 기존 버전은 모두 유지된다
### 문서의 이전 버전 보기
  - 해당 문서의 역사 페이지에서 문서의 모든 버전을 볼 수 있다
  - 특정 버전을 클릭하면 그 버전의 문서를 볼 수 있다

## 작업 순서
1. 초기 설정
2. 컴포넌트 작업
3. 페이지 병합
4. 테스트
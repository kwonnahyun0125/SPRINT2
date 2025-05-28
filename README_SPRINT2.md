# 🛍️ SPRINT2 - 상품 및 게시글 OOP + API 프로젝트

## 📖 프로젝트 개요

> **상품 및 게시글 객체지향 모델링과 CRUD API 연동**
ESM 모듈을 기반으로 JavaScript 클래스 설계, 상속 구조 구현, 그리고 fetch API를 통한 서버 통신을 학습하는 프로젝트입니다.

---

## 📁 디렉토리 구조

```
SPRINT2/
├── main.js                 # 앱 초기 실행 파일
├── Product.js              # 상품 클래스 정의
├── ElectronicProduct.js    # 전자제품 상품 클래스 (Product 상속)
├── ProductService.js       # 상품 관련 API 함수 정의
├── Article.js              # 게시글 클래스 정의
├── ArticleService.js       # 게시글 관련 API 함수 정의
├── package.json
└── package-lock.json
```

---

## 🧩 핵심 기능

### 📌 상품 클래스 (`Product.js`)
- 기본 정보: 이름, 설명, 가격, 태그, 이미지 배열
- 찜 기능: `favorite()`, `favoriteCount`

### 📌 전자제품 클래스 (`ElectronicProduct.js`)
- `Product` 상속
- 제조사(manufacturer) 프로퍼티 추가

### 📌 게시글 클래스 (`Article.js`)
- 기본 정보: 제목, 내용, 작성자, 생성일
- 좋아요 기능: `like()`, `likeCount`

---

## 🔗 API 연동

| 기능 | 메서드 | 경로 |
|------|--------|------|
| 상품 목록 조회 | `GET` | `/products?page=&pageSize=&keyword=` |
| 상품 상세 조회 | `GET` | `/products/:id` |
| 상품 등록 | `POST` | `/products` |
| 상품 수정 | `PATCH` | `/products/:id` |
| 상품 삭제 | `DELETE` | `/products/:id` |
| 게시글도 위와 동일 구조 | `ArticleService.js` 참고 |

**Base URL**:  
- 상품: `https://panda-market-api-crud.vercel.app/products`  
- 게시글: `https://panda-market-api-crud.vercel.app/articles`

---

## 🚀 실행 방법

1. 의존성 설치  
```bash
npm install
```

2. 실행 (nodemon 기반 자동 재실행)
```bash
npm run dev
```

3. 결과 확인: 콘솔 로그로 클래스 인스턴스 및 API 결과 확인

---

## 🧪 테스트 예시

```js
const product1 = new Product("무선 이어폰", "설명", 10000, ["태그"], ["img1.jpg"]);
product1.favorite();
console.log(product1.favoriteCount); // → 1

const article1 = new Article("제목", "내용", "작성자");
article1.like();
console.log(article1.likeCount); // → 1
```

---

## 📌 개발 포인트 요약

- ESM `import/export` 기반 모듈 설계
- 클래스 상속과 캡슐화 (`#field`, `getter`)
- `fetch` 기반 비동기 API 통신 구조화
- 인스턴스와 API를 연결한 초기화 로직 구현

---

## 🔧 향후 개선 아이디어

- `axios`로 전환하여 에러 핸들링 강화
- 날짜 포맷 처리(`toLocaleString` 등)
- 게시글/상품 별도 페이지나 Vue, React 연계
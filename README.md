# 백엔드 프레임워크 REST API 과제

## 1. 프로젝트 개요
- **Base URL**: `/api/v1/items` & `/api/v3/items`
- **구현 기능**: REST API CRUD 및 미들웨어(LoggingInterceptor) 적용

## 2. API 명세 및 테스트 결과 (총 8개)

| Method | Endpoint | Status Code | 설명 |
| :--- | :--- | :--- | :--- |
| **GET** | `/api/v1/items/1` | `200 OK` | 아이템 단건 조회 성공 |
| **GET** | `/api/v1/items/999` | `404 Not Found` | 존재하지 않는 아이템 조회 |
| **POST** | `/api/v1/items` | `200 OK` | 신규 아이템 생성 성공 |
| **POST** | `/api/v1/items/test-1` | `405 Method Not Allowed` | 허용되지 않은 메서드 요청 |
| **PUT** | `/api/v1/items/1` | `200 OK` | 아이템 수정 성공 |
| **PUT** | `/api/v3/items/test-500` | `500 Internal Server Error` | 서버 에러 시뮬레이션 |
| **DELETE** | `/api/v3/items/1` | `200 OK` (or `204`) | 아이템 삭제 성공 |
| **DELETE** | `/api/v3/items/test-503` | `503 Service Unavailable` | 서비스 점검 시뮬레이션 |

## 3. 미들웨어 (Middleware)
- `LoggingInterceptor`를 통해 요청/응답 로그 기록 구현
# Biz Support Matcher API 명세서

## 1. 인증/회원 API
| 기능 | Method | Endpoint | 인증 | 설명 |
|---|---|---|---|---|
| 회원가입 | `POST` | `/api/auth/signup` | X | 새로운 회원 가입 |
| 로그인 | `POST` | `/api/auth/login` | X | 이메일과 비밀번호로 로그인 |
| 로그아웃 | `POST` | `/api/auth/logout` | O | 로그인 상태 종료 |
| 내 정보 조회 | `GET` | `/api/users/me` | O | 로그인 회원 정보 조회 |
| 내 정보 수정 | `PATCH` | `/api/users/me` | O | 로그인 회원 정보 수정 |
| 회원 탈퇴 | `DELETE` | `/api/users/me` | O | 회원 탈퇴 |

## 2. 사업체 API
| 기능 | Method | Endpoint | 인증 | 설명 |
|---|---|---|---|---|
| 내 사업체 등록 | `POST` | `/api/businesses` | O | 로그인 회원의 사업체 등록 |
| 내 사업체 조회 | `GET` | `/api/businesses/me` | O | 로그인 회원의 사업체 정보 조회 |
| 내 사업체 수정 | `PATCH` | `/api/businesses/me` | O | 로그인 회원의 사업체 정보 수정 |


## 3. 지원사업 공고 API
| 기능 | Method | Endpoint | 인증 | 설명 |
|---|---|---|---|---|
| 지원사업 목록 조회 | `GET` | `/api/announcements` | X | 지원사업 공고 목록 조회 |
| 지원사업 상세 조회 | `GET` | `/api/announcements/{announcementId}` | X | 특정 지원사업 공고 상세 조회 |
| 지원사업 검색 | `GET` | `/api/announcements/search` | X | 키워드로 지원사업 검색 |
| 지원사업 필터 조회 | `GET` | `/api/announcements` | X | 지역, 지원분야, 대상 등 조건으로 필터링 |

## 4. 관심사업 API
| 기능 | Method | Endpoint | 인증 | 설명 |
|---|---|---|---|---|
| 관심사업 등록 | `POST` | `/api/favorites/{announcementId}` | O | 지원사업을 관심 목록에 등록 |
| 관심사업 목록 조회 | `GET` | `/api/favorites` | O | 로그인 회원의 관심사업 목록 조회 |
| 관심사업 여부 조회 | `GET` | `/api/favorites/{announcementId}` | O | 해당 공고의 관심 등록 여부 확인 |
| 관심사업 삭제 | `DELETE` | `/api/favorites/{announcementId}` | O | 관심 목록에서 지원사업 삭제 |

## 5. 매칭 API
| 기능 | Method | Endpoint | 인증 | 설명 |
|---|---|---|---|---|
| 맞춤 지원사업 목록 조회 | `GET` | `/api/matches` | O | 로그인 회원의 사업체 정보를 기준으로 매칭된 지원사업 조회 |
| 매칭 결과 상세 조회 | `GET` | `/api/matches/{announcementId}` | O | 특정 지원사업의 매칭 결과 및 조건별 결과 조회 |
| 매칭 실행 | `POST` | `/api/matches` | O | 현재 사업체 정보를 기준으로 지원사업 매칭 실행 |

## 6. AI 분석 API
| 기능 | Method | Endpoint | 인증 | 설명 |
|---|---|---|---|---|
| AI 적합도 분석 실행 | `POST` | `/api/ai-analysis/{announcementId}` | O | 사업체 정보와 특정 지원사업을 AI로 분석 |
| AI 분석 결과 조회 | `GET` | `/api/ai-analysis/{announcementId}` | O | 저장된 AI 분석 결과 조회 |
| AI 분석 결과 목록 조회 | `GET` | `/api/ai-analysis` | O | 로그인 회원의 AI 분석 결과 목록 조회 |


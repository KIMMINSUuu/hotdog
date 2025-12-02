# HotDog

반려동물과 함께하는 시간을 늘리기 위한 산책 애플리케이션

## 프로젝트 소개

HotDog는 반려동물과 함께하는 산책을 더욱 즐겁고 편리하게 만들어주는 Flutter 기반 모바일 애플리케이션입니다. 실시간 위치 추적, 산책 경로 기록, 커뮤니티 기능, 반려동물 용품 쇼핑 등 다양한 기능을 제공합니다.

## 주요 기능

### 산책 관련 기능
- **실시간 위치 추적**: GPS를 활용한 실시간 위치 확인
- **산책 경로 기록**: Google Maps API를 통한 산책 경로 시각화
- **걸음 수 측정**: Pedometer를 활용한 걸음 수 카운팅
- **산책 목표 설정**: 일일 걸음 수 목표 설정 및 달성률 확인

### 커뮤니티 기능
- **게시판**: 반려동물 정보 공유 및 소통
- **리뷰**: 산책 장소 및 제품 리뷰 작성
- **Q&A**: 질문과 답변 커뮤니티

### 쇼핑 기능
- **반려동물 용품 쇼핑**: 다양한 카테고리의 제품 탐색
- **제품 상세 정보**: 영양 성분, 재료 정보 제공
- **평점 및 리뷰**: 제품별 사용자 평가

### 사용자 관리
- **회원가입/로그인**: 사용자 인증 시스템
- **내 정보 관리**: 프로필 및 반려동물 정보 관리
- **비밀번호 찾기/재설정**: 계정 보안 기능

### AI 기능
- **이미지 인식**: TensorFlow Lite 기반 Siamese 모델을 활용한 이미지 처리

## 기술 스택

### Frontend
- **Flutter** (SDK 3.5.4+): 크로스 플랫폼 모바일 앱 개발
- **Dart**: 주요 개발 언어

### 상태 관리
- **Provider**: 전역 상태 관리

### 지도 및 위치
- **google_maps_flutter**: Google Maps 통합
- **geolocator**: GPS 위치 정보
- **geocoding**: 주소 변환
- **location**: 위치 서비스
- **flutter_polyline_points**: 경로 폴리라인 표시

### 데이터베이스
- **mysql_client**: MySQL 데이터베이스 연결

### 머신러닝
- **tflite_flutter**: TensorFlow Lite 모델 실행
- Siamese 모델을 활용한 이미지 처리

### UI/UX
- **percent_indicator**: 진행률 표시
- **flutter_rating_bar**: 별점 평가
- **image_picker**: 이미지 선택 및 촬영

### 기타
- **pedometer**: 걸음 수 측정
- **http**: REST API 통신
- **shared_preferences**: 로컬 데이터 저장
- **permission_handler**: 권한 관리
- **intl**: 국제화 및 날짜 포맷팅

## 프로젝트 구조

```
lib/
├── main.dart                    # 앱 진입점
├── Start.dart                   # 시작 화면
├── Home.dart                    # 홈 화면
├── Walking.dart                 # 산책 화면 (지도)
├── Mapscreen.dart              # 지도 화면
├── Login.dart                  # 로그인
├── Register.dart               # 회원가입
├── FindPassword.dart           # 비밀번호 찾기
├── ResetPassword.dart          # 비밀번호 재설정
├── MyInfo.dart                 # 내 정보
├── MyInfoModi.dart             # 내 정보 수정
├── Community.dart              # 커뮤니티
├── ReviewDetail.dart           # 리뷰 상세
├── QnA.dart                    # Q&A 목록
├── QnADetail.dart              # Q&A 상세
├── QnAWrite.dart               # Q&A 작성
├── Shop/                       # 쇼핑 관련
│   ├── Shop.dart
│   ├── ProductClass.dart
│   ├── product_grid.dart
│   ├── product_item.dart
│   └── product-detail/
├── User_Provider.dart          # 사용자 상태 관리
├── DBconnector.dart            # 데이터베이스 연결
├── Siamese.dart                # 이미지 인식
└── auth.dart                   # 인증

assets/
├── images/                     # 이미지 리소스
├── profile/                    # 프로필 이미지
├── location/                   # 장소 이미지
├── locations.json              # 장소 데이터
└── siamese_model.tflite        # AI 모델
```

## 설치 및 실행

### 사전 요구사항
- Flutter SDK 3.5.4 이상
- Dart SDK
- Android Studio / Xcode (플랫폼에 따라)
- MySQL 데이터베이스

### 설치 방법

1. 저장소 클론
```bash
git clone https://github.com/your-repo/hotdog.git
cd hotdog
```

2. 의존성 설치
```bash
flutter pub get
```

3. Google Maps API 키 설정
- `lib/Walking.dart` 파일의 API 키를 자신의 키로 변경
```dart
String APIKEY = 'YOUR_GOOGLE_MAPS_API_KEY';
```

4. 앱 실행
```bash
flutter run
```

## 개발 환경 설정

### Android
- `android/app/build.gradle` 파일에서 minSdkVersion 확인
- Google Maps API 키를 `android/app/src/main/AndroidManifest.xml`에 추가

### iOS
- `ios/Runner/Info.plist`에 위치 권한 및 Google Maps API 키 추가
- Podfile 업데이트: `cd ios && pod install`

## 권한 설정

앱 실행을 위해 다음 권한이 필요합니다:
- 위치 정보 (GPS)
- 카메라
- 사진 라이브러리
- 인터넷 연결

## 데이터베이스

MySQL 데이터베이스를 사용하며, `DBconnector.dart`에서 연결을 관리합니다.

## 기여 방법

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 라이선스

이 프로젝트는 개인 프로젝트이며 공개 배포를 허용하지 않습니다. (`publish_to: 'none'`)

## 개발자

- 프로젝트 이름: HOTDOG
- 버전: 1.0.0+1


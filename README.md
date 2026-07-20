# 방셀 SNS 게시판

방문자는 이미지를 업로드하거나 게시할 수 없고, 관리자가 GitHub에 등록한 게시물만 SNS 피드 효과로 표시되는 정적 게시판입니다.

## 파일 구성

- `index.html` : 방문자가 보는 게시판
- `posts.json` : 게시물 목록과 표시 정보
- `images/` : 게시물 이미지와 프로필 이미지 폴더

## 게시물 추가 방법

1. 게시 이미지와 프로필 이미지를 `images` 폴더에 업로드합니다.
2. `posts.json`의 `posts` 배열 맨 위에 새 항목을 추가합니다.
3. GitHub에 커밋하면 GitHub Pages에 자동 반영됩니다.

예시:

```json
{
  "name": "게시판 주인",
  "userId": "@board_owner",
  "date": "2026. 7. 21.",
  "image": "images/post-002.jpg",
  "avatar": "images/avatar.jpg",
  "caption": "새 게시물 내용",
  "ratio": "portrait",
  "likes": 30,
  "isNew": true,
  "comments": [
    { "user": "viewer01", "text": "댓글 예시" }
  ]
}
```

## ratio 값

- `portrait` : 4:5
- `square` : 1:1
- `landscape` : 16:10
- `auto` : 원본 비율

## GitHub Pages 설정

1. 저장소에 파일을 업로드합니다.
2. **Settings → Pages**
3. **Deploy from a branch**
4. `main` 브랜치와 `/ (root)` 선택
5. 저장 후 생성된 주소로 접속

방문자는 게시 기능 없이 이미지, 좋아요, 댓글, 공유, 저장 연출만 볼 수 있습니다.

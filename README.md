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
  "images": [
    "images/post-002-1.jpg",
    "images/post-002-2.jpg"
  ],
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


## GitHub Pages 설정

1. 저장소에 파일을 업로드합니다.
2. **Settings → Pages**
3. **Deploy from a branch**
4. `main` 브랜치와 `/ (root)` 선택
5. 저장 후 생성된 주소로 접속

방문자는 게시 기능 없이 이미지, 좋아요, 댓글, 공유, 저장 연출만 볼 수 있습니다.


## 여러 이미지 게시물

`images` 배열에 파일 경로를 여러 개 넣으면 방문자가 좌우 스와이프 또는 화살표 버튼으로 한 장씩 넘겨볼 수 있습니다.

```json
"images": [
  "images/photo-1.jpg",
  "images/photo-2.jpg",
  "images/photo-3.jpg"
]
```

각 이미지는 원본 비율에 맞춰 높이가 자동 조절됩니다. 우측 아래 다운로드 버튼은 현재 보고 있는 이미지만 저장합니다.

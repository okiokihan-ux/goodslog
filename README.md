# GoodsLog + Claude AI 자동 입력

## 기능
- 기존 GoodsLog 주문 기록/업체 관리/달력/백업 기능
- 이미지 영수증·거래명세서에서 Claude API로 업체명, 주문일, 주문번호, 품목, 수량, 금액 추출
- 추출 결과를 주문 입력 폼에 반영하고 사용자가 확인/수정 후 저장
- 개인정보(이름, 주소, 전화번호)는 추출하지 않도록 프롬프트에서 제한
- PDF는 기존 브라우저 OCR로 처리하고, 이미지 파일은 서버 함수에서 Claude 분석

## 배포 방법 (Netlify)
1. 이 폴더 전체를 GitHub 저장소에 올립니다.
2. Netlify에서 **Add new site → Import an existing project**를 선택하고 저장소를 연결합니다.
3. Site configuration → Environment variables에서 `ANTHROPIC_API_KEY`를 추가합니다. 키는 HTML에 넣지 말고 반드시 Netlify 환경 변수에만 저장하세요.
4. 사이트를 배포합니다. 이미지 자동 입력은 Netlify 사이트 주소에서 열었을 때 동작합니다.
5. 새 주문 → 이미지 영수증/거래명세서 첨부 → **영수증·거래명세서 자동 입력**을 누릅니다.

## 주의
- Claude API 사용에는 Anthropic 계정과 API 사용료가 필요할 수 있습니다.
- 추출 결과는 틀릴 수 있으므로 저장 전에 상품명·수량·금액·날짜를 확인하세요.
- API로 전송되는 이미지는 Claude가 분석합니다. 민감한 문서 사용 전 개인정보를 가리세요.
- 이 버전은 기존 브라우저 로컬 저장소 기반이며, 로그인/PC-모바일 동기화는 포함하지 않습니다.

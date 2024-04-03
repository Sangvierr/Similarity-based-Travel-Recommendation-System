# 제11회 문화데이터 활용 경진대회
K-관광 활성화를 위한 국내외 도시 유사도 분석 및 여행지 추천
: Similarity-based-Travel-Recommendation-System

1. Preprocessing & EDA
- 개괄 : 2022년 데이터를 기준으로 데이터 전처리 진행
- 사용데이터 
: 2022년 동반유형 키워드, SNS 언급량, 문화관광축제 분석, 유형별 검색건수, 2018~23년 방문자수 추이 (한국관광 데이터랩), 좌표, 주소 (카카오 API)

2. Similarity
- LDA (Latent Dirichlet Allocation)를 통해 유사도 계산을 위한 해외 여행지 토픽 파악
- Compositional Data Clustering을 통해 국내 도시 카테고리 재조정
- Jensen Shannon Divergence를 이용해 해외, 국내 여행지간 유사도 계산

3. Recommendation System
- 주변 지역 명소를 함께 여행한다는 특징을 고려해 추천 점수 계산 시 Distance와 Boundary를 모두 고려한 공간가중치 부여
- 해외·국내 도시 유사도, 트렌드 점수, 방문자수 계절성 등을 추천 변수로 사용
- 여행지 추천에 대한 사용자의 반응을 입력 받아 가중치를 업데이트하는 Online Learning 적용
- 관광지 수와 방문자 수로 마할라노비스 거리를 계산해 해외 유명 도시와 유사한 국내 도시 중 관광지로써 가능성은 있지만 실제 관광 수요가 적은 도시에 유사도 기반 관광 제언

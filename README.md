# FITCHWI (React와 Spring을 활용한 MVC 패턴의 웹 사이트)

<b>프로젝트 소개</b>
    <ul>
        <li>MBTI를 활용하여 회원들에게 취미를 추천하고, 온라인 소통 및 오프라인 모임 공간을 조성할 수 있는 사이트 제작</li>
        <li>인원 : 4명</li>
        <li>기간 : 2022/11/30 ~ 2023/01/16</li>
    </ul>
<br/>
<b>개발도구</b>
    <ul>
        <li>ERD 설계 – https://www.erdcloud.com/</li>
        <li>DB – MySQL, WorkBench</li>
        <li>IDE - IntelliJ, Visual Studio Code</li>
        <li>Back end - Java 11, Spring boot 2.7.6, JPA</li>
        <li>Front end - React.js 18.2.0, Node.js 16.16.0</li>
        <li>버전관리 - GitHub</li>
    </ul>

<h2>역할 및 담당</h2>

<b>공통역할</b>

<ul>
 <li>각자 구상한 아이디어로 진행된 회의를 통해, 프로젝트 기획 및 정의</li>
 <li>데이터베이스 정의, 설계 및 구현</li>
 <li>프로젝트 전, 각자 역량에 따른 역할 분배</li>
 <li>공통으로 사용 될 디자인, 메인 컬러 선택(MUI - react component library 활용)</li>
</ul>
<br/>
<p>개인 역할</p>

<h4>1. 메인페이지</h4>

 <p>1) 취미 및 모임 추천</p>
 
<ul>
    <li>로그인 완료 시, sessionStorage에 아이디, 닉네임, 프로필사진의 url, MBTI 정보를 저장하도록 처리하여</li>
    <li>저장된 MBTI 정보와 관심사를 기반으로 해당 유형의 회원들이 많이 참여한 모임 또는 관심사를 추천하도록 함</li>
    <li>비 로그인 시 랜덤함수를 사용해서 16가지 MBTI중 하나가 선택되도록 처리함</li>
</ul>

 <o>2) 이달의 회원</o>
 
<ul>
    <li>해당 기간내에 작성한 게시물이 가장 많은 4명을 조회하여 프로필 이미지와 함께 간단한 소개</li>
    <li>반응형 웹 형태로 페이지의 크기에 따라 소개글과 프로필 -> 프로필 -> 뱃지 형태의 사진과 순위로 표현되게 처리함</li>
</ul>

<p>3) 다양한 카테고리</p>

<ul>
    <li>카테고리 선택 시 데이터베이스 내에서 해당 유형의 모임들을 불러오고 프론트 영역에서 filter와 map 함수를 활용해서 최신, 추천 모임들을 출력하도록 처리함</li>
    <li>React의 State 변경감지를 통해 다른 카테고리를 선택하였을 경우 페이지 새로고침 없이 처리되도록 하였음</li>
    <li>카테고리의 이미지들을 unsplash API를 활용하여 불필요한 이미지 저장을 최소화하였음</li>
</ul>

<h4>2. 검색 기능</h4>

<ul>
    <li>헤더 영역에 검색 아이콘을 배치해서 모든 페이지에서 검색 기능을 이용할 수 있도록 처리함</li>
    <li>기본적으로 JPA의 동적쿼리를 활용해서 다양한 키워드를 통한 검색 기능을 구현함</li>
</ul>

<p>1) 검색 메인페이지</p>
<ul>
    <li>검색은 props(properties)의 propTypes와 isRequired를 사용하여 검색어의 자료형과 필수 요소들을 확인하도록 처리함</li>
    <li>등록된 피드중에 가장 많은 좋아요를 받은 피드들을 모아둔 인기 카테고리와 가장 최근에 작성된 피드들을 모아둔 최신 카테고리로 분류해서 보여지도록 처리함</li>
    <li>클릭시 해당 피드의 상세 보기 페이지로 이동</li>
</ul>

<p>2) 검색결과</p>

<ul>
    <li>헤더 영역 하단에 고정된 형태의 작은 검색바를 추가해서 검색결과 페이지에서도 검색을 할 수 있도록 처리함</li>
    <li>검색어를 sessionStorage에 저장하여 이전 페이지로 이동하더라도 검색결과가 저장되도록 처리함</li>
    <li>한 번의 검색으로 데이터베이스 내의 모임, 클럽, 피드들을 조회한 후 검색결과의 원하는 항목을 클릭했을 때 해당 유형으로 State를 변경하여 조회된 결과들을 보여주는 방식으로 처리함</li>
    <li>해당 검색어에 해당하는 검색결과가 없을 경우, "해당 검색어의 검색결과가 없습니다" 메시지를 출력하고 해당 유형의 메인페이지 바로가기 링크를 출력하도록 처리함</li>
</ul>

<h4>3. SNS 기능</h4>

<p>1) 공유해요 메인페이지</p>

<ul>
    <li>기본적으로 공유해요의 모든 기능은 로그인 후에 가능하고, 비 로그인 시 ‘로그인 후에 이용할 수 있습니다’ 라는 문구를 출력하고 로그인 페이지로 이동하도록 처리함</li>
    <li>메인페이지 좌측에는 사이드 바 형태로 카테고리 항목을 추가하였고, 원하는 카테고리를 선택 시 해당 카테고리의 피드들을 출력하도록 처리함</li>
    <li>우측에는 sessionStorage에 저장되어 있는 회원의 MBTI 정보를 활용하여 동일한 MBTI를 가진 회원들을 추천하고 해당 회원을 클릭하면 회원의 마이페이지로 이동하도록 처리함, 또한 피드를 작성할 때 추가한 태그 중에서 가장 최근에 추가한 태그들을 출력해서 현재 어떤 주제의 피드들이 올라오고 있는지 확인할 수 있도록 처리함</li>
</ul>

<p>2) 피드 작성</p>

<ul>
    <li>좌측 하단에 Tooltip 효과를 가진 "+" 아이콘을 추가해서 해당 아이콘을 클릭 시 Modal 방식으로 피드를 등록할 수 있도록 처리함</li>
    <li>피드 등록 시 서버로 넘어가는 Form 객체에 Content-Type을 application/json 타입으로 설정하고 multipart/form-data 속성을 추가하였음</li>
    <li>피드 등록 시 사진을 첨부하면 사진의 개수에 따라 미리보기 형태를 달리하여 최대 4장의 이미지를 보여지도록 처리함</li>
    <li>피드에 태그 추가 시 등록되어 있는 태그를 검색하여 추가하거나 원하는 태그가 없다면 태그 추가 버튼을 통해 직접 입력하여 추가할 수 있도록 처리함</li>
    <li>작성하려는 피드의 유형에 따라 공개 범위를 다르게 처리하여서 참여중인 모임의 후기 피드 또는 일반적인 일상 공유의 피드 두 가지로 나뉘어 저장하도록 처리함</li>
</ul>

<p>3) 피드 불러오기 및 상세페이지</p>

<ul>
    <li>React 환경에서의 무한 스크롤 기능을 구현하여 스크롤이 페이지 하단에 닿았을 때 IntersectionObserver을 활용하여 서버로 다음 페이지에 해당하는 피드를 요청하고 이전의 State에 concat 하는 형태로 5개의 피드들을 추가하도록 처리함</li>
    <li>피드는 Card 형태로 구성하였고 상단에는 작성자의 프로필 이미지와 닉네임, moment 라이브러리를 활용하여 피드 작성시간을 출력하였음</li>
    <li>피드의 사진이 한 장일 경우에는 이미지를 클릭하였을 때 상세페이지로 이동하게 되고, 한 장 이상일 경우에는 Carousel 라이브러리를 활용하여 슬라이드 형태로 처리함</li>
    <li>피드를 불러오는 과정에서 "loading" State를 추가해서 데이터가 넘어오지 않은 경우에는 backdrop 효과를 적용하여 스크롤 이벤트가 발생할 수 없도록 처리함</li>
    <li>참여중인 모임에 관련된 피드일 경우 피드 이미지 하단 영역에 참여중인 모임의 정보가 출력되고 해당 영역을 클릭 시 모임의 상세페이지로 이동함</li>
    <li>피드에 등록되어 있는 태그를 클릭하면 해당 태그로 검색한 검색결과 페이지로 이동하도록 처리함</li>
</ul>

<p>4) 피드 댓글 및 좋아요</p>

<ul>
    <li>sessionStorage에 저장된 회원 이메일과 비교하여, 자신이 등록한 피드인지 아닌지를 구분한 후 기능을 구분하였음 ex) 피드 삭제 및 수정 / 좋아요 및 댓글, 신고</li>
    <li>좋아요 버튼 클릭 시 토글 형식으로 좋아요 상태에 따라서 두 가지의 아이콘으로 출력하도록 처리함, 또한 좋아요의 수가 바로 반영되어 처리되고 텍스트를 클릭하게 되면 좋아요를 누른 회원들의 목록이 Modal 형식으로 출력됨</li>
    <li>sessionStorage에 저장된 회원 이메일과 댓글을 작성한 회원 이메일이 같은 경우 댓글을 삭제할 수 있도록 처리하였고, 댓글이 5개 이상일 경우 가장 먼저 등록된 댓글과 "댓글 X개 모두 보기" 버튼이 추가되며 해당 버튼 클릭 시 피드 상세페이지로 이동하고 작성된 모든 댓글들이 보여지도록 처리함</li>
</ul>

<h4>4. 다양한 오픈 API 연동</h4>

<p>1) 챗봇</p>

<ul>
    <li>커뮤니티 서비스 특성 상 발생할 수 있는 문의사항, Q&A, 환불관련 규정에 대해 처리할 수 있도록 챗봇을 사용하였고, 그 중 채널톡 API를 활용하였음</li>
</ul>

<p>2) 아임포트 결제기능</p>
<ul>
    <li>결제 및 환불 서비스를 위해 아임포트(I,mport)를 연동시켰음</li>
</ul>




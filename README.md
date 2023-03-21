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

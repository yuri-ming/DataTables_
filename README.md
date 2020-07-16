# DataTables_
#### DataTables 알기 
#### 1. DataTables 란?
##### - HTML의 <table>을 데이터 그리드 형식을 사용하기 위한 라이브러리
##### - 사용하기 위해 jQuery 필요
##### - 아파치 톰캣을 사용한 서버구현
#### 2. DataTables 사용하기 - DataTables JS, CSS, jQuery 필요
##### 1) HTML <head> 부분에 추가 
```HTML
<link rel="stylesheet" type="text/css" href="DataTables/datatables.min.css"/>
```
##### 2) <script> 코드 추가
```HTML
<script src="https://code.jquery.com/jquery-3.2.1.min.js"></script>
    <script type="text/javascript" src="DataTables/datatables.min.js"></script>
    <script>
        $(document).ready( function () {
        $('#example').DataTable();
        } ); 
    </script>
```
##### 3) html파일과 DataTables 파일을 `tomcat>webapps>ROOT`에 넣고 파일 실행! 
##### - 기본 예제 출력
!(C:\Users\82105\Desktop\dt\datatables.jpg)
---
#### 3. DataTables 관리하기
!(C:\Users\82105\Desktop\dt\function.jpg)
##### 1) 기능 숨기기
```HTML
<script>
        $(document).ready( function () {
        $('#example').DataTable({
            lenghtChange: false,  //표시 건수 기능 숨기기
            searching : false,  //검색 기능 숨기기
            ordering: false,  //정렬 기능 숨기기
            info : false,  //정보 표시 숨기기
            paging : false  //페이징 기능 숨기기
        });
        } ); 
    </script>
```
##### 2) 초기 항목 정렬하기 
```HTML
<script>
        $(document).ready( function () {
        $('#example').DataTable({
            order:[[0,"asc"], [1,"desc"]] //[[열번호,정렬순서]] (열번호는 0부터 시작)
            //첫번째 항목 오름차순 정렬 + 두번째 항목 내림차순 정렬
        });
        } ); 
    </script>
```
##### 3) 스크롤바와 넓이 설정
```HTML
<script>
        $(document).ready( function () {
        $('#example').DataTable({
            scrollX:true,
            scrollY:200,  //스크롤바 설정
            
            //열 넓이 설정
            columnDefs:[
                {targets :1, width :100 }  //두번째 항목 넓이를 100px로 설정
            ]
        });
        } ); 
    </script>
```
##### 4) 컬럼 항목 숨기기
```HTML
<script>
        $(document).ready( function () {
        $('#example').DataTable({
            scrollX:true,
            scrollY:200,  //스크롤바 설정

            columnDefs:[
                {targets:0, visible:false}, //1번째 항목의 열을 숨김
                {targest:1, width:100 }  //2번째 항목의 넓이를 100px로 설정
            ]
        });
        } ); 
    </script>
```
##### 5) 표시 건수 설정
```HTML
<script>
        $(document).ready( function () {
        $('#example').DataTable({
            lengthMenu:[10,20,30,40,50],  //표시건수를 10건 단위로 설정

            displayLength:50,  //기본 표시 건수를 50건으로 설정(표시할때 보여줄 기본값)
            scrollX:true,
            scrollY:200,
            columnDefs:[
                {targets:0, visible:false},
                {target:1, width:100}
            ]
        });
        } ); 
    </script>
```
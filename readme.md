# 중간고사 과제

# 취약점 식별 및 시큐어 코딩

## 회원기능

### 회원가입

1. **join.php**
    1. 입력값 검증 미흡
        
        ```php
        // 수정 전
        <input type="text" name="id">
        <input type="password" name="pw">
        <input type="email" name="email">
        ```
        
        ```php
        // 수정 후  
        <input type="text" name="id" maxlength="16" required pattern="[a-zA-Z0-9_]{4,16}">
        
        <input type="password" name="pw" maxlength="20" required autocomplete="off">
        
        <input type="email" name="email" maxlength="50" required>
        ```
        
2. **join_action.php**

```php
<input type="hidden" name="param_csrf_token" autocomplete="off" value="<?= htmlspecialchars($_SESSION['SESSION_CSRF_TOKEN'], ENT_QUOTES, 'UTF-8') ?>">
	
```

### 로그인/로그아웃

- **login.php**
- **login_action.php**
- **logout.php**

### **비밀번호 변경**

- **change_pw.php**
- **change_pw_action.php**

## **게시판 기능**

- **board_list.php**
- **board_list_search.php**

### **게시글 목록 조회 및 검색**

- **write.php**
- **write_action.php**
- **delete.php**

### **게시글 작성 및 삭제**

- **write.php**
- **write_action.php**
- **delete.php**

### **게시글 상세보기 및 파일 다운로드**

- **view.php**
- **download.php**

### **게시글 수정**

- **modify.php**
- **modify_action.php**
- **modify_file_delete_action.php**

### **댓글 작성 및 삭제**

- **write_action_sub.php**
- **delete_sub.php**

### **추천 기능**

- **star.php**
- **star_sub.php**

## **관리자 기능**

### **관리자 기능**

- **board_list_admin.php**
- **delete_admin.php**

## **기타**

### **세션관리**

- **session_protect.php**

# Web_Security_CCNY

1. (Required) Vulnerability Name or ID: Authenticated Stored Cross-Site Scripting(XSS1)
  - [x] Summary: 
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.2.3
  - [x] GIF Walkthrough: 
    - <img src='XSS.gif' title='XSS' width='' alt='' />
  - [x] Steps to recreate: 
    - Create a new post, and then put this code ```<a onmouseover= "alert('I got you!')" >click here</a>``` in the content link. Finally click link to show message in the preview of post.
  - [x] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/browser/branches/4.2/src/wp-includes/class-wp-editor.php?rev=33361)

### 2. (Required) Large File Upload Error XSS
  - [ ] Summary: In WordPress before 4.7.5, a cross-site scripting (XSS) vulnerability exists when attempting to upload very large files, because the error message does not properly restrict presentation of the filename. 
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.7.5
  - [ ] GIF Walkthrough:
  ![](Exploit2.gif)
  - [ ] Steps to recreate:
  I created a large image file and uploaded the manipulated name to pass a script:

  In this page:
  ```http://wpdistillery.vm/wp-admin/media-new.php```
  uploaded image with name:
  ```nature<img src=x onerror=alert(1)>.png```
  - [ ] Affected source code:
    - [Link](https://github.com/WordPress/WordPress/commit/8c7ea71edbbffca5d9766b7bea7c7f3722ffafa6)

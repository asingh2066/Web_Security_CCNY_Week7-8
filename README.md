# Web_Security_CCNY_WEEK_7and8_LAB
Time spent: **10** hours spent in total, including setup

> Objective: Find, analyze, recreate, and document **three vulnerabilities** affecting an old version of WordPress
### 1. (Required) WordPress <= 4.3 - Authenticated Shortcode Tags Cross-Site Scripting (XSS)
  - [x] Summary: A stored, or persistent, cross-site scripting vulnerablilty which allows remote attackers to inject arbitrary web script or HTML by abusing the way unclosed HTML elements during the processing of shortcode tags are mishandled.
    - Vulnerability types: Stored cross-site scripting (XSS)
    - Tested in version: 4.1.1
    - Fixed in version: 4.3
  - [x] GIF Walkthrough:
  ![](XSS3.gif)

  - [x] Steps to recreate: Create a new page or a post and place the following line in the body:

    ```
    [caption width="1" caption='<a href="' ">]</a><a href="http://onmouseover='alert(1)'">Over here!</a>
    ```

    When another user hovers over the text, the injected code is executed.

  - [x] Affected source code: [branches/4.1/src/wp-includes/post.php](https://core.trac.wordpress.org/browser/branches/4.1/src/wp-includes/post.php)

### 2. (Required) Large File Upload Error XSS
  - [ ] Summary: In WordPress before 4.7.5, a cross-site scripting (XSS) vulnerability exists when attempting to upload very large files, because the error message does not properly restrict presentation of the filename. 
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.7.5
  - [ ] GIF Walkthrough:
  ![](XSS2.gif)
  - [ ] Steps to recreate:
  I created a large image file and uploaded the manipulated name to pass a script:

  In this page:
  ```http://wpdistillery.vm/wp-admin/media-new.php```
  uploaded image with name:
  ```nature<img src=x onerror=alert(1)>.png```
  - [ ] Affected source code:
    - [Link](https://github.com/WordPress/WordPress/commit/8c7ea71edbbffca5d9766b7bea7c7f3722ffafa6)
    
    ### 3. (Required) Authenticated Stored Cross-Site Scripting
  - [ ] Summary: Cross-site scripting (XSS) vulnerability in WordPress before 4.2.3 allows remote authenticated users to inject arbitrary web script or HTML by leveraging the Author or Contributor role to place a crafted shortcode inside an HTML element, related to wp-includes/kses.php and wp-includes/shortcodes.php.
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.2.3
  - [ ] GIF Walkthrough:
  ![](XSS3.gif)
  - [ ] Steps to recreate: 
  To recreate this exploit, I placed the following script in the HTML edit post box:
  ```
  <a href="[caption code=">]</a><a title=" onmouseover=alert('test')  ">link</a>
  ```
which resulted in the execution of a script without any click or otherwise.
  - [ ] Affected source code:
    - [Link](https://klikki.fi/adv/wordpress3.html)

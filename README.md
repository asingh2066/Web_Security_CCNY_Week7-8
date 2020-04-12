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

2. (Required) Vulnerability Name or ID: Unauthenticated Stored Cross-Site Scripting (XSS2)
  - [x] Summary: 
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.2.4
  - [x] GIF Walkthrough: 
    - <img src='XSS2.gif' title='XSS2' width='' alt='' />
  - [x] Steps to recreate: 
    - View a new post, and insert code ```<abbr title='Web......cedric' onmouseover='alert(1)' style='position:fixed;top:0;left:0;width:100%;height:100%'>``` on the comment uder this post. Then it shows 1 when you view the comment of this post in future. 
  - [x] Affected source code:
    - [Link 3](https://cedricvb.be/post/wordpress-stored-xss-vulnerability-4-1-2/)

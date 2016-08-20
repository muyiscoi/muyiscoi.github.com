---
id: 928
title: Salt and Hash demystified
date: 2016-07-25T08:00:26+00:00
author: muyiscoi
layout: post
guid: http://muyiscoi.com/?p=928
permalink: /?p=928
categories:
  - Technology
tags:
  - cryptography
  - engineering
  - hashing
  - hashing and salting
  - php
  - salting
  - security
  - web development
---
[<img class="aligncenter size-full wp-image-934" src="https://muyiscoi.com/blog/wp-content/uploads/2016/07/salt-hash-password-java.png" alt="salt-hash-password-java" width="569" height="130" />](https://muyiscoi.com/blog/wp-content/uploads/2016/07/salt-hash-password-java.png)

If you&#8217;ve been on the internet in the last couple of years, you must have come across an article or twenty about yet another data breach where sensitive information like user account passwords and credit card details were stolen by &#8220;hackers&#8221;. It is becoming an almost daily occurrence now, and no company is immune, irrespective of how large they are or how sophisticated their infrastructure is.

The only sure way to mitigate against this eventuality is to ensure that all data is well protected by implementing well documented and industry accepted security best practices. One of such practices, and the subject of this blog, is &#8220;hashing and salting&#8221; of passwords in a database.

<!--more-->

# **Hashing**

Hashing is a cryptographic process where a one-way operation is carried out on data in order to generate a unique fingerprint known as a hash. Since the operation is one way, the original data cannot be recovered from its hash. The hash is however unique to that data and any changes made would lead to a different hash being generated.
  
As a result of this property, hashing algorithms are incredibly useful in verifying data integrity in a process known as [non-repudiation](https://en.wikipedia.org/wiki/Non-repudiation). One popular use of hashing in this sense is in verifying file downloads before installation in order to ensure that they have not been tampered with via a man-in-the-middle attack or some other means.

Another use of hashing is to verify user access to a resource without knowing any knowledge of the key required to access said resource. This is particularly useful for websites and other applications that require user login. As mentioned earlier, it is safe to assume that your website is likely to be hacked into and your database stolen at some point during its life cycle. It is therefore extremely irresponsible to store passwords in plain-text in the database table of your site.

Hashing algorithms can be used to generate a cryptograhic hash of the password at the time of account creation, and that is what will be stored in the database. This ensures that a unique key string is stored for each user, and that string cannot theoretically be reversed back to the original plain text since hashing is a one way operation.
  
Whenever the user tries to login, the plain-text password entered into the login form is again hashed with the same algorithm and the generated hash is compared with the hash stored against that particular user in the database. If both hashes match, login is confirmed and the user gains access to the resource. This ensures that the website/app can verify user credentials without actually knowing said credentials.

There are several Hashing algorithms available today such as MD5, SHA-1, SHA-2, bcrypt etc. Security vulnerabilites have been detected and exploited in the MD5 and the SHA algorithm s. As a result, bcrypt and better is currently recommended for all hashing purposes.

For hashing to work, the same algorithm has to be used to generate the hash everytime, in order for the hashes to remain the same and be comparable. This introduces another problem, as two user accounts having the same passwords will have the same hash. Attackers can therefore build up dictionaries of hashes of popular passwords using the different hash algorithms available. Salting passwords were introduced to further improve on the security of hashes.

# Password Salt

While storing passwords in hashes are way more secure than plain text, hashed passwords are still susceptible to other forms of attack such as dictionary and rainbow attacks. In order to mitigate against this, a password salt has to be added to the password before hashing. A salt in cryptography is a random data included as an additional input to a function that hashes a password.

In order for salts to be useful, it has to be randomly generated and unique to each user. The salts don&#8217;t have to be encrypted, and can be stored in plain text on the database. The salt increases the unique property of the hash meaning that even if two user accounts have the same passwords, their hash would be different as a result of them having two different randomly generated salts.

# Conclusion

Salting and hashing combine to provide important security for user credentials on the web. They are important technologies and techniques that should be well understood by anyone venturing into this field. This article has only scratched the surface on what can be understood about them, and there are several resources online where more information can be found.

Thankfully, as a web developer, you do not need extensive understanding of cryptography in order to implement a user account system utilizing password hashing and salting. Most major programming languages either have built-in functions, or popular third party functions that can be easily called to carry out the process for you. A popular one in PHP is [password_hash](http://php.net/manual/en/function.password-hash.php).

**Relevant Links**

  * <https://en.wikipedia.org/wiki/Hash_function>
  * <https://crackstation.net/hashing-security.htm>
  * <https://en.wikipedia.org/wiki/Salt_(cryptography)>
  * <http://security.stackexchange.com/questions/17421/how-to-store-salt>
  * <http://php.net/manual/en/function.password-hash.php>
  * [https://en.wikipedia.org/wiki/Hash\_function\_security_summary](https://en.wikipedia.org/wiki/Hash_function_security_summary)
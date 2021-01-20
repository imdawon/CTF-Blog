![PAR Banner](https://camo.githubusercontent.com/8092861699721c936072e1325c0134e87de7797d5ffd0d9a7b04e4437edf05eb/68747470733a2f2f692e696d6775722e636f6d2f55494879664a692e706e67)
# Paranormal Activity Reporter

Created during my full stack bootcamp in early 2020.

## 0x01 - Site Anatomy
* Forum application
 * Ran on Express, Handlebars, MySQL
* Had user auth and session management
* Had 8 different topics you could post under

During development, I was aware of proper password storage practices. Each user password was hashed via bcrypt at 10 rounds, pretty beefy against a brute force attack.
Other than that, the app was developed to meet a deadline, and security wasn't even on our radar. Our bootcamp taught us about avoiding SQLi when creating SQL queries, and that was it.

## 0x02 - The Vulns

### Painful Sign Up Bug

![PAR SignUp](par2.jpg)\
*Upon entering the site, you are greeted by the sign up page.*

Using a unique email address, entering a password, and clicking "Sign Up" is all it takes to get in!\
But what if a malicious person wanted info about an **exisiting** user?\

![SignUpBug](parsignupbug.JPG)\
*Lucky for them, we somehow package the entire user object and send it back in the error response.*

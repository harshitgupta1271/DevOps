Jenkins Setup on Mac

🔧 Setup
java -jar jenkins.war
# Admin Password: xyz
👤 Create Admin User
Username: harshitGupta
Password: xyz
Email: hgupta1271@gmail.com
🛠 Tool Configuration
JDK: /opt/homebrew/Cellar/openjdk@17/17.0.16/libexec/openjdk.jdk/Contents/Home
Git: /opt/homebrew/bin/git
Maven: /Users/harshit/Tools/apache-maven-3.9.11
▶️ Job Setup
Create new Maven job.
Configure Git repo: https://github.com/harshitgupta1271/Selenium-Hybrid-Framework.git
Set Goals: maven test
Click on Build Now.
You can also use a local pom.xml path instead of Git URL.



   


















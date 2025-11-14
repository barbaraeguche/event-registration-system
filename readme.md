# event registration system 🎟️
a web-based event management system that allows users to browse upcoming events, register for them, and manage their
registrations. this project demonstrates both **servlet-based** and **jsp-based** implementations of the same
functionality. this was made as part of my **soen 387 assignment 1**.

## features 👾
- **dual implementation approach:** complete functionality available in both servlet and jsp versions.
- **event browsing:** view a list of upcoming events with details (date, location, description, pricing).
- **registration management:** register for events with customizable participant count (1-5 participants).
- **session-based cart system:** maintain registration state across multiple pages using http sessions.

## challenges faced 💢
- **setting up servlet environment:** configuring the servlet container (tomcat) and ensuring proper deployment context.
- **dual implementation:** maintaining feature parity between servlet and jsp versions.

## what I learned 💭
- **java servlets:** request/response handling, servlet lifecycle, and programmatic html generation using `PrintWriter`.
- **jsp (java-server pages):** embedding java code in html pages using scriptlets and expression language.
- **servlet annotations:** using `@WebServlet` for modern servlet configuration instead of xml.
- **mvc pattern:** separating concerns between model (event, registration), view (jsp/servlets), and data layer.
- **jakarta ee:** working with the modern jakarta ee 10 namespace (vs. legacy javax.servlet).

## running the project 🏁
to get the project up and running on your local machine, follow these steps:

### prerequisites
- **ensure [jdk](https://www.oracle.com/java/technologies/downloads/) is installed:** this project uses jdk v24.
- **application server:** apache tomcat 10.x or higher (supports jakarta ee 10).

### setup instructions
#### 1. clone the repository
```bash
git clone https://github.com/barbaraeguche/event-registration-system.git
```

#### 2. navigate to the project directory
```bash
cd event-registration-system
```

#### 3. configure your ide (intellij idea example)
**a. set up tomcat:**
- download and install [apache tomcat 10.x](https://tomcat.apache.org/download-10.cgi)
- go to **intellij idea → settings → build, execution, deployment → application servers** (on mac)
- click **+** and add your tomcat installation directory

**b. build the project with maven:**
- open the terminal in intellij (or use your system terminal)
- run the following command to clean and build the project:
```bash
mvn clean package
```
- this will create the `target` directory with the war file needed for deployment

**c. configure the run configuration:**
- click **run → edit configurations**
- click **+** and select **tomcat server → local**
- name it (e.g., "event-registration-system")
- in the **server** tab:
    - set **http port** to `8080` (or your preferred port)
    - set the **url** to `http://localhost:8080/event-registration-system/`
- in the **deployment** tab:
    - click **+** and select **artifact**
    - select `event-registration-system:war exploded`
    - set **application context** to `/event-registration-system`
- click **apply** and **ok**

#### 4. run the application
- click the **run** button (green play icon) or press **⌃R** (control+r on mac)
- wait for tomcat to start and deploy the application
- your browser should automatically open to: [http://localhost:8080/event-registration-system/](http://localhost:8080/event-registration-system/)

## tech stack ✨
- **java 24**
- **jakarta servlet 6.0** (jakarta ee 10)
- **jsp 3.1**
- **apache tomcat 10.x**
- **html5 & css3**
- **http sessions**

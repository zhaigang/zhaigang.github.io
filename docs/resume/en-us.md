# resume-Gunther Zhai

<table border="0">
            <td style="width:60%">
                <table border="1" >
                    <tr>         <td>name</td>         <td>gunther zhai</td>    <td>sex</td>         <td>man</td> </tr>
                    <tr>         <td>addr</td>         <td>Shaanxi, 712000, China</td>    <td>birth day</td>         <td>1992.05.02</td> </tr>
                    <tr>         <td>phone</td>         <td>+86 19992980478</td>    <td>email</td>         <td>zhaigang666@outlook.com</td> </tr>
                    <tr>         <td>education</td>         <td>Bachelor degree</td>    <td>college</td>         <td>Shangluo College, China</td> </tr>
                    <tr>         <td>major</td>         <td>electronic infomation engineering</td>    <td>length for service</td>         <td>10 years</td> </tr>
                </table>
            </td>
    </table>

## introduce myself

<div style="display:flex;justify-content:space-between;align-items:center">
  <div style="flex: 1; margin-right: 20px;">
    I have  ten years of work experience. I majored in electronic information engineering in college. After graduation, I have been working in software development using C++ and Python. My main work directions are website back-end development and data processing. I am proficient in using Django, Docker, and SQL. I can communicate with other colleague with basic english, Even my english is not fluent, but i also want to join a international team, to talk and cooperate with people from different country. I really hope to get an opportunity to work remotely and have an English-speaking working atmosphere.
</div>
  <div>
    <img src="images/CV/me.jpg" style="max-width: 200px; border-radius: 8px;"/>
</div>
</div>



## skills

1. python
   * backend
     * django/orm/jwt
   * test
     * pytest
     * nosetests
       * allure
2. native sql and storage procedures
   * index, trigger, view, window function etc.
   * fineBI
3. docker and docker compose
4. c++
   * STL
   * QT
5. linux
6. vue.js/react/tailwind.css (a little)

## project experience

### network test platform <font size ="2">    2024.09-now</font>

* **Project description**
  
  Our customer is a cloud computer merchat, the bussiness accross from scale compute, virtual cloud network, and other cloud service.We are major work on endpoint to endpoint scenaior test. 
  
  1) learn product document and clearify bussiness logic,design business test network topology. 
  
  2) enhance test framework stablity, analysis problem from test tools or product,makesure test system can find the version problem quickly. analysis test cost, decrease test cost.
  
  3) analysis and summarize the problemld from test system ,design the next generation test system. 
  
  4) undertake the bussiness test before online, design test plan.

### claw machine platform <font size ="2">    2023.08-2024.07</font>

* **Project description**
  
  this company is product Amusement equipment, in order to imporve marketing capabilities, need to build four system support. they are living game app, Advertising delivery system，Merchant management system,User gaming system. 
  
  1) living game app. This system is used by the person in charge of shopping mall amusement activities to organize on-site users to play various games, such as climbing frames, and competing to give away amusement resources. 
  
  2) Advertising delivery system.This subsystem is used for merchants who purchase the company's claw machine to place and manage their own advertisements on the claw machine's own screen, or to settle funds for advertisements issued by the company. 
  
  3) Merchant management system. This system is the company's core system and is used to manage merchants' inventory and procurement, statistical analysis of consumption of various gaming resources, merchant gaming revenue settlement, and docking gaming facilities to issue instructions, etc. 
  
  4) User gaming system.In this system, users purchase game rights, activate game equipment, and place some user-oriented advertisements in the store.
     
     * part for my job 
       * Sort out the company's needs, classify the business, and design the system structure. 
       * Backstage table structure design and code development. 
       * Routine server maintenance and optimization of performance issues

### Cloud computing machine proformance check platform<font size ="2">    2022.10-2023.08</font>

* Project description
  * this project mainly use to check the cloud computer proformance, such as CPU, GPU, io, network. Out put quantitative inspection report. 
  * this platform has three part:
    * front-end: show the report on the web page.
    * backend: use Django framwork, manage the user login/logout, create/drop/show the check task, collect the check result. use the SDK provided by the  cloud server  supplier, manage the task used machine.
    * check-tools: write by pure python, used for install on the target machine, and create the real check task, collect the run log.
* part for my job
  * front-end develop, use React+Antd framwork,write the functional page and  chart report.
  * backend develop, use Django + rest + docker to writed. features developed include multi cloud server sdk adapter, asynchronous task management component, performance data collect and  analysis component.
  * Participate in requirements analysis, task assessment, task module splitting, etc.

### Mobile phone proformance analysis platform<font size ="2">    2021.10-2022.10</font>

* Project description
  
  * The project is to support the troubleshooting of problems such as heating ,freezing, CPU used too heigh of mobile phones in the stage before they are released, and to improve the public opinion evaluation of mobile phones.  
  * This project has a simple front-end struct,  this project focus is on many performance inspection tools. Such as:
    * Thread time consumption comparison tool: collect two phone run log when they run the same app, collect the memory function stack, compare the time taken for pushing and popping functions into the stack during operation.
    * Application startup time comparison tool: The application startup video collected from multiple mobile phones was identified frame by frame, and the startup time report was output.

* part for my job
  
  * Participate in the design of performance improvement tool structure, develop and maintain the WEB version of the performance problem locating toolbox, and provide quick problem locating and delimiting tools for the test department.（django+celery+vue）
  * The thread time comparison tool uses the cpu run logs captured by the simperf tool to locate time-consuming functions and compare differences among multiple products.（py+pyqt+js）
  * Maintain the data quality of the big data platform, including partial log analysis, dimension analysis, user habit analysis, etc.（py+re）
  * Maintain the performance positioning software developed earlier and undertake the development of various automation tools.

### Code control platform development<font size ="2">   2020.10-2021.09</font>

* Project description
  
  * The company's custom development of linux involves a large number of submitted codes and requires version, baseline, and performance management, so it needs to develop a management platform to support its business.

* part for my job
  
  * Access git commit records and incoming records, etc., to develop energy efficiency measurement interfaces.
  
  * Code quality, development efficiency analysis platform. (django& Stored Procedures)
  
  * Development of authority control system. (django+rest)
  
  * Test report automatic generation tool development.

### Smart wearable device development <font size ="2">   2020.04-2020.10</font>

* Project description
  * The project is mainly to adapt to the rapid release of the watch, replace the UI framework and project architecture.
* part for my job
  * Sort out the original code and extract the UI process. Data Presentation Logic (c++)
  * UI development based on the new framework (c++)
  * Troubleshoot problems at the bottom of UI and maintain daily versions
  * Project support tool development (python,log grab, compression tool)

### Improved integrated build capabilities 2018.11-2020.04</font>

* Project description
  
  * The project mainly delivers the unified version of the software that needs to be delivered in the European 5G project. After the completion of the first phase of the project, the main problems to be solved are that the overall dependency chain of the project is not clear enough, the compilation platform and the environment image cannot be completely isolated, and the version release is standardized. 

* part for my job
  
  * Switch scons compilation projects (python+scons) on a one-phase makefile basis.
  
  * Distributed compilation system development, single project granular elastic compilation system (background python/c++/mysql,web python).
  
  * bug fixes in historical software, new requirements development (python/c++)
  
  * Cross-platform support for the original tool, involving c++/c system call modifications.
  
  * Some python tools cannot be re-adapted from cross-platform tripartite packages.
  
  * Sorted out the original compilation process, wrote a clearer compilation process (bat/shell/cmake), uniformly switched to makefile, and sorted out the overall dependencies.

### Coal mine production quality analysis platform<font size ="2">   2017.08-2017.11</font>

* Project description
  * As a peripheral system of production, the main function of the analysis platform is to extract and load the monitoring data of various systems, including support pressure, fan power, mining progress, downhole personnel, gas pressure and other monitoring data to the data warehouse, compile stored procedures according to Party A's business rules, separate and summarize the data, and provide excuse data for the supervision system and statements. The project mainly uses python + stored procedure to complete background data mining analysis, uses finebi as the foreground for data presentation, and uses PyQt to develop dynamic report tools.
* part for my job
  * Assist query system, based on Qt development of C/S structure, access the background PLSQL business logic, business presentation, including real-time early warning analysis.
  * Warehouse data quality inspection system, using PLSQL to validate warehouse data, including system abnormal fluctuation filtering and abnormal data risk analysis.
  * Basic model development, subject summary of data extracted from the business system according to the degree of data dependence and redundancy, to provide simple and efficient basic data for subsequent data interfaces.
  * Development of supervisory data interface, analysis of data interface provided by supervisory system, model analysis of warehouse data, and construction of interface model.

### Digital mine monitoring system <font size ="2">   2017.05-2017.08</font>

* Project description
  * Enterprises are required to further strengthen the automated management and analysis of mines, accelerate the digitization process of mines, set up a data monitoring center project, and require the project to summarize and analyze the data scattered at various grassroots levels, improve the utilization efficiency of equipment and personnel, strengthen risk management and control for mining, and rationally allocate market and transportation conditions. The project mainly uses c++ development, using sqlserver for data storage.
* part for my job
  * Data acquisition system Data access: from the underlying sensor access to the database, and integrated into the data management center.
  * Storage for different types of data and data sizes.
  * Perform real-time data redundancy checks and curve data integration.
  * Communicate with equipment management center to refine user needs.
  * Train on-site maintenance personnel and Party A's business personnel.

### Development of transaction settlement platform<font size ="2">   2016.08-2017.05</font>

* Project description
  * For each transaction, there are merchant collection, platform distribution and channel settlement. The project mainly consists of foreground reports and background data interface. Personally responsible for background data extraction, analysis and mining, providing T+1 analysis report and T+0 real-time profit report for interface development. The project is mainly developed using python and stored procedures.
* part for my job
  * Assist channel business personnel to confirm liquidation rules, confirm workload, and develop background stored procedures.
  * Report system development, developed according to the analysis needs of merchants on day, month and year, and provided data interface to the front desk.
  * Docking analysis requirements, daily verification of report system, transaction inspection.

### POS machine trading system development<font size ="2">   2016.05-2016.08 </font>

* Project description
  * The company's research and development of cash register needs to optimize the purchased POS machine and cash register trading system, docking business channels, in order to meet the latest business needs. Encrypt and decrypt transactions sent from terminals and connect to upstream transaction channels. The project mainly uses c++ for development in linux system and oracle database.
* part for my job
  * ADAPTS the encryption machine purchased by the company to encrypt and decrypt messages in the original transaction receiving system.
  * Follow up message format analysis, adapt to revenue channels, parse additional information based on 8583 messages, and adapt to local databases.
  * oracle datastage is used for Dr System construction and routine maintenance.

### Data warehouse development<font size ="2">   2015.05-2016.05</font>

* Project description
  * The company is mainly engaged in the development and integration of banking system trading systems, and the department of personal intelligence Business mainly develops data warehousing systems.
* part for my job
  * Data extraction change layer development (DataStage+sql)
  * Data topic layer development, modify the model according to upstream requirements (stored procedure)
    Supervise report development and daily audit report development (oracleBI+ stored procedures)
  * Docking business personnel, learning business and clear requirements, document landing.
## work experence

| company                                      | worktime        |
| -------------------------------------------- | --------------- |
| isoftstone Technology Co., Ltd.              | 2024.09-now     |
| Wanvision Manufacturing Technology Co., Ltd. | 2023.08-2024.07 |
| Beyondsoft Technology Co., Ltd.              | 2022.10-2023.8  |
| archermind Technology Co., Ltd.              | 2021.10-2022.10 |
| isoftstone Technology Co., Ltd.              | 2018.11-2021.09 |
| Hejiexun Technology Co., Ltd.                | 2015.05-2018.08 |
# Proven Tips and Tricks for UI Developer

Collection of tips abd tricks that should be considered during UI development along with the sample code.

  <p>I have extensively worked on the latest JavaScript frameworks & libraries like React with redux, Angular 1 & 2+, Ember with Ember data, node with express.js, Jquery, D3.js, RxJS, Ionic etc throughout the last 8 years. After getting expertise on UI technologies I wanted to share my knowledge about “How UI applications should be?”. Interestingly I kept it so generic that it will be applicable to every UI application regardless of domain, framework, technology etc.</p>
  <p>These can be considered as checkpoints or guidelines in UI application development. The priority of guidelines will be changed depending on the project and business need. One Application may not focus on browser compatibility and responsiveness but others may insist on it. It will always be the business decisions. Nowadays few of the guidelines are taken care of by JavaScript frameworks or plugins we use.</p>

I have divided tips abd tricks into multiple sections for better understanding. Let's walk through it without further delay.

## 1. Platform:
It mostly considers the physical aspects on which the application will run
1. **Browser Compatibility**
    - Application should work properly on any browser.
    - Decide & test on targeted browsers like chrome, firefox, safari, IE etc
    - Also need to consider the minimum supported version for each browser
    - www.caniuse.com can be used to check supported browser versions.
    - e.g. Check which browser supports “localStorage” [here](https://caniuse.com/?search=localStorage)

2. **Different Resolutions / Responsive design**
    - Application should work properly on different screen sizes. 
    - Should be tested for responsiveness, Always use Chrome Tools to check for responsiveness and multiple device sizes
    - Libraries to use: Twitter Bootstrap, Media Query

3. **Small Screen Support**
    - Should have left/right sidebar for better accessibility
    - Should feel like native application

4. **Keyboard Accessibility**
    - Should be able to navigate the entire UI using keyboard only
    - tabindex will help to order the elements
    - Use hotkeys for common features like search, submit etc

5. **Polyfills whenever required**
   - Supporting older browser versions

## 2. UI Aesthetics:
It will focus on look and feel of application
1. **Consistency**
    - Use consistent width, height, color, font, padding, theme etc.
    - e.g. Use same width and height for all buttons (Use primary color for OK/Yes button and default color for Cancel/No button)

2. **User Interaction** - Design a interaction model with
    - Minimum user clicks
    - Avoid number of clicks whenever possible
      e.g use radio buttons (1 click) for gender selection instead of dropdown (2 clicks)
    - Maximum information should be visible to user
      e.g use radio buttons (all options are visible) for gender selection instead of dropdown (only selected option is visible). Use dropdown when we have more options e.g. countries, cities list

3. **Use Favicon**
    - favicon shows in the browser title bar

4. **Alphabetical Ordering** of lists, table rows
    - sorting may depend on the important column
    - e.g. for order list sort desc on orderDate, for user list sort asc on name or id 

5. **Search, Sort, Filter features** (May be available with pagination plugins like datatables, ui-grids)
    - Most commonly used features
    - Use debounce in search and filter -> debounce will wait method execution until user stops typing

6. **Show loading** during API calls, Async operations
    - Disable and show loading inside the clicked button until we get the response.
    - If we don’t disable the button then the user may click it multiple times.

7. **Use of Animation** while hiding, showing, translating element etc
    - Should be aware of hidden/newly shown elements. It drags user’s attention

8. **Prefill Input** and use appropriate default values
    - Reduces the human efforts
    - Defaults can be derived from other inputs, user profile, geo location etc

## 3. Coding Standards 
It is very basic and equally important while developing any application.
1. **Format Code**
    - Always format your code for better readability.

2. Use **Proper Comments**
    - Comments provides more details about the code and will help to understand working of code

3. Use **Proper Variable and Method names**
    - Proper naming conventions will help you (if you are visiting code after a long time) and others to maintain code.

4. **Never Duplicate Code**
    - Move duplicated code to parameterized method or new method in shared class
    - Duplicate code makes the application fragile and non-maintainable

5. **Input Validations** 
    - Setting min - max limits
    - Update the default values as per need
    - Check the behavior for boundary conditions.
    - Check for all valid, invalid, symbols, numbers
    - Better to use RegEx for validation

6. trim() and **Sanitise each input field** before API call
    - Clean the input values before sending to server to save
    - Attacker may add 

7. **Global Error / Exception Handling**
    - It avoids sudden termination of application
    - Catch the exception in promises as well

8. **Console and Network tab**
    - Always check for exceptions, errors in console and fix them
    - Check for the deprecated features and remove it’s use
    - e.g 404 errors for missing images
    - Always check the Network tab for API calls if by mistake hitting the same API multiple times.

## 4. Important Integrations / Libraries
We can say the ecosystem of your code
1. **Selection of JavaScript framework**
    - Select JavaScript framework based on need
    - No of pages, static vs dynamic content
    - Application size
    - Key features and important third party integrations
    - Target audience like mobile, desktop, platform
    - e.g. React, Angular, Ember etc

2. **Code Build Pipeline**
    - Static code analysis
    - Minification of js, css
    - Run unit tests
    - Most of the time it is provided with JavaScript framework itself
    - e.g. grunt, gulp, webpack

3. **Authentication and Authorization** - route guards, interceptors
    - Most of the applications have public, private, role based routes
    - Public route -> accessible to everyone - /login page
    - Private route ->accessible to authenticated user - /profile page
    - Role based route -> accessible to admin user - /users page (admin can see & operate on all the users)

4. **Localization / i18n**
    - Separates out text/label from code
    - All the static labels will be available at single place to modify
    - Easy to support new language
    - Libraries to use: i18next, ngx-translate for Angular

5. **Use of Cookies, localStorage, sessionStorage, indexedDB**
    - Key-value storage on browser
    - Use the appropriate storage based on sensitivity, size, duration of expiration of data

6. Use **State Management**
    - Central place for data which allows data management easy
    - e.g. Redux, Ngxs for Angular

7. **Logging** for easy debugging
    - Changing log level to debug an issue will help a lot
    - e.g. ionic-logging-service for Ionic

8. **Research before using third party library** 
    - Like Number of github stars, last commit date, Number of contributors, active bugs, active community, license, bundle size
    - If you use non active library then you may face issue and nobody will be there to help

## 5. Dev Environment
It will be used only in dev setup but surely will help you a lot.
1. Use **Stub Server**
    - Actual backend API may not provide you the response for all the cases.
    - It is easy to mock the response using stub server and test all possible cases.
    - e.g. Jsonstub

2. Use **Dev Extensions**
    - For easy debugging
    - e.g. Each JavaScript framework has their extension Ember, Angular, React, Redux DevTool

## 6. Performance
It is a key metric to any web application. People will not use an application if it takes a long time to load, slow or hangs in between.
1. Use **Sprite Sheets**
    - Single image has multiple icons
    - Reduces server calls,  loading time and increases performance

2. **Pagination for large data**
    - Reduces the response time and bandwidth
    - No need of pagination if we have few records and won’t grow over time (< 50)
    - Use Client side pagination if we have few hundreds of records
    - Use Server side pagination if we have thousands of records 
    - Libraries to use: Depends on the JavaScript you use. E.g. Datatable with jQuery, ui-grid with angular.js

3. Use **Web Workers**
    - Allows to put long running and computationally intensive tasks on the background without blocking UI
    - If we do not use workers then the UI will be unresponsive and will not render anything during the computation task as the main thread will be blocked by that task.
    - Sorting example with and without web workers: http://afshinm.github.io/50k/

4. Use **Lazy Loading** whenever possible
    - Delaying the load or initialization of the resources until they are actually needed
    - Improves performance

5. **Request caching** to minimize server hits
    - There may be few requests whose response doesn't change frequently can be cached in browser
    - e.g. ionic-cache for Ionic

## 7. Automation Testing and Profiling
Test coverage can be considered as the health of your application.
1. **Unit Testing**
    - Automated tests will save a lot of time. It greatly helps while bug fixing or additional changes to your code.
    - e.g. Jasmine and Karma

2. **JavaScript Profiling**
    - Helps to find out whether your application gets slower or even will it crash? over a period of time.
    - Discovers memory leaks, CPU consumption

## 8. Security
Security of users data is top most priority. Following security standard practices reduces the risks. 
1. Use **secure protocol** while interacting with server (for http -> https, ws -> wss)
    - To avoid man-in-the-middle-attack

2. **Static Code Analysis**
    - It will help in improving the code quality. It will highlight bugs, security vulnerabilities.
    - e.g. sonarQube, SonarLint

3. **Security Testing**
    - It reveals security flaws
    - Use CSP header
    - e.g. ZAP Proxy

4. **Periodically review the libraries** and update to latest version
    - You may start developing the application with the latest libraries but after some time those libraries will be outdated. It will be better to periodically review and update to the latest version whenever possible.
    - Update provides important security fixes and latest features
    - It is non-functional work but a must do exercise. 
    - If you don’t do it periodically then a major jump to the latest version will be time consuming and may have a lot of breaking changes.
    - npm audit - will help to identify the npm packages



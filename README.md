## Dynamic Web 1 Week 6 Homework Instructions

**Free Geo Ip App Project 3:** counts toward **65%** of the final grade.

**Week 6 Homework Part 2:** counts toward **20%** of the final grade.

## Free Geo Ip App Project 3:

- For the **_third project_** in the **course**, we are going to **_re-build_** the `Free Geo Ip App` that I **_built_** for `lecture 6` of this course. However, I don't want you to **_exactly_** **replicate** what I have done. I only want to make sure that you can render the `Geolocation Api` (`navigator.geolocation`) **_when available_** in the **browser**, and **_at least_** ONE of the **properties** of the **Free IP Geolocation Api** we are using in the application.

- To view the **properties** **_available_** on the **Free IP Geolocation Api** in `JSON` **format** (as that is what we are using), please visit [Free IP Geolocation Api - JSON](https://freegeoip.app/json/). To view the **Free IP Geolocation Api** **_homepage_**, please visit [freegeoip.app/](https://freegeoip.app/).

## Project 3 Set Up:

- Use this folder and rename it `geo-ip-api`. This is where the `files/folders` for your `third project` will **_reside_**, and the `local repository` you will be **pushing** to `Github`.
- Then add a `.txt` **file** for your **_answers_**. There is **no code** involved in the answers for this week's homework.
- `git clone https://github.com/interglobalmedia/geo-ip-app.git` this repository to your `laptop/desktop`.
- Then make sure to `rm -rf .git`. You don't want to keep my .git, as doing so will throw an error. You will see that when you do execute `rm -rf .git` in Terminal, that the `master branch` will no longer appear, and if you execute the ls -a command, you will see that the .git folder has disappeared as well.
- Now you are **_ready_** to `initialize git` in **_this folder_**. Initialize the `local repository/folder` of your **new project** with the `git init` command. When you are **ready** to **_push_** anything to your `remote repository` (**remember** to **_create_** a `repository` on **Github**, and **_name_** it with the **same name** you use in your `local project folder`), remember to use the `git add .` command **_first_**, then the `git commit` command, then the `git remote add origin nameofyourremoterepositoryurl`, and **_lastly_**, `git push -u origin master`. After that, you don't have to use `-u` again. Only when you **_first_** **push** your `local changes` to **remote**. After that, you just **execute** `git push origin master`.
- You can **_view_** `Part 2` of this `homework` **_below_** the **instructions** for `Project 3`.
- Create an `index.html` file in the root of your folder. If you are using `VS Code`, add `html5 boilerplate` by **_typing_** `html` and then selecting `html:5` from the `suggestions dropdown` that subsequently **appears**.
- Create a `main.css` file in the **_root_** of your `project folder`. If you want to structure that differently, that is totally fine.
- Create a `main.js` file in the root of your project folder. If you want to structure that differently, that is totally fine.
- Inside the `index.html` file, make sure to **_add_** your `main.css` file to the `head` **element**.
- Inside the `index.html`, make sure to add your `main.js` file to the `src` **attribute** of a `script` **tag** which should be placed **_right above_** the **_closing_** `body` **tag**.
- **Add** an `element` (ul, for example, or div) to your `index.html` with **_either_** an `id` **attribute** with the `id` **name** as its `value` or a `class` **attribute** with a `class name` as its `value`. Also make sure to **_add_** any other `elements` necessary in your application to your `index.html`. You can use my `index.hml` in my [project repository](https://github.com/interglobalmedia/geo-ip-app) as a guide. But please **_make sure_** that what is **in** the `index.html` matches what you are using in your `JavaScript` file or in your `CSS` file.
- You will need to **_create_** some **variables** needed in your `main.js` file. They should be `located` at the `top` of the **file**:
  - You need to **create** a **_variable_** which stores as its **value** `document.getElementById()` in which you will **_pass_** the `id` **name** you **set** to the `element` you want to **use** as the **container** for the `data` **_fetched_** from the **Free IP Geolocation Api**. Please refer to my `main.js` file on the [geo-ip-app](https://github.com/interglobalmedia/geo-ip-app/blob/master/scripts/js/main.js) repository on **Github**. It should look something like this:

```javascript
const ul = document.getElementById("geoIp");
```

**Create** your **_own_** **variable** `name` and **id** `name`.

- You need to **create** a **_variable_** which stores as its **_value_** the `url` to the **Free IP Geolocation Api** where we will be **retrieving** our `data` **_from_**. Please refer to my `main.js` file on the [geo-ip-app](https://github.com/interglobalmedia/geo-ip-app/blob/master/scripts/js/main.js) repository on **Github**. It should look something like this:

```javascript
const geoIpUrl = `https://freegeoip.app/json/`;
```

**Create** your **_own_** **variable** `name` .

- Next, `declare` and `initialize` a `function` which will **_house_** **all** the `code` for **_fetching_** the **Geolocation Api** and the **Free IP Geolocation Api**. **Pass** a `parameter` to this `function` which you will **use** **_later_** in the `body` of the `function`. You **do** **_this_** so as to make it **readily available** to the **_whole body_** of this `parent function`. I call the `parameter` I **_pass_** to my `getGeoIP()` **function** `ip`. Please refer to my `main.js` file on the [geo-ip-app](https://github.com/interglobalmedia/geo-ip-app/blob/master/scripts/js/main.js) repository on **Github**.

  At this point, the `function declaration` should look something like this:

```javascript
function getGeoIP(ip) {}
```

- Within this `function`, you will **first need** to make a `call` to the `fetch()` **method** and **_pass_** the **variable** which **stores** the **Free Geolocation Ip Api** `url` to the `fetch()` **method**. Please refer to my `main.js` file on the [geo-ip-app](https://github.com/interglobalmedia/geo-ip-app/blob/master/scripts/js/main.js) repository on **Github**.

  **_Now_** your `parent function` should look something like this:

```javascript
function getGeoIP(ip) {
  fetch(geoIpUrl);
}
```

- Next you have to `chain` your **_first_** `.then()` block to the `fetch()` method and **_pass_** a `res` **object** into it.
- **_Then_**, using an `arrow function`, you will **return** that `res` **object** and set the `.json()` method on it. With **_this_** `.then()` block, I did **_not_** **add** `{}` **_after_** the `fat arrow` of the `arrow function`, because the `code block` **_fit_** on `one line`. Please refer to my `main.js` file on the [geo-ip-app](https://github.com/interglobalmedia/geo-ip-app/blob/master/scripts/js/main.js) repository on **Github**.

  At this point, your `parent function` should look something like this:

```javascript
function getGeoIP(ip) {
  fetch(geoIpUrl).then(res => res.json());
}
```

- **_Next_**, you will `chain` your **_second_** `.then()` **method** to the first `.then()` method and **_pass_** in a **new parameter** calling it whatever you want (I **_call_** **mine** `geoIp`). Please refer to my `main.js` file on the [geo-ip-app](https://github.com/interglobalmedia/geo-ip-app/blob/master/scripts/js/main.js) repository on **Github**.

  At this point, your `parent function` should look something like this:

```javascript
function getGeoIP(ip) {
  fetch(geoIpUrl)
    .then(res => res.json())
    .then(geoIp => {});
}
```

- The **_new_** `parameter` just **passed** to the **_second_** `.then()` block should be followed by **_another_** `fat arrow` indicating an `arrow function` is being used, which should contain `{}`, as shown above. This is **_because_** there will be many lines of `code` within this `.then()` block.
- Next, we pass the `geoIp` **variable** as the `value` of the `ip` `parameter/variable` we **_initially_** passed in to the `parent function` when we declared it. Please refer to my `main.js` file on the [geo-ip-app](https://github.com/interglobalmedia/geo-ip-app/blob/master/scripts/js/main.js) repository on **Github**.

  At this point, your `parent function` should look something like this:

```javascript
function getGeoIP(ip) {
  fetch(geoIpUrl)
    .then(res => res.json())
    .then(geoIp => {
      ip = geoIp;
    });
}
```

As you **_may recall_** from the `Using The Fetch Api With The Free Geo Ip Api` [slide deck](https://interglobalmedia.github.io/fetch-geo-ip-api/#/9), the `geoIp` **parameter/variable** we **_pass_** to the **second** `.then()` block **_contains_** the `data` **_passed_** into it **from** the `res` object **_returned_** to our **app** in the **_form_** of an `HTTP response` **retrieved** from the `request` to the `Free IP Geolocation Api` by the `fetch()` method, which is then **_transformed_** into `JSON` by **setting** the `.json()` **method** on it (`res.json()`), and then the **data** from `res.json()` is **_passed into_** our **new** `geoIp` (or whatever you want to call it) `parameter`.

- Next, I `console.log(ip.country_code)`. `.country_code` is one of the **properties** of the `Free IP Geolocation API`, and I just want to make sure that I have been **_successful_** in **retrieving** the `data` from the `Api`. And **_yes_**, I was! Below is a screenshot of the `Chrome Developer Tools` of the app hosted on `Github gh-pages`. `US` is printed to the console, and that refers to `console.log(ip.country_code)`.

![Chrome Developer Tools screenshot of ip.country_code](/images/country_code.png)

- It is **_important_** to **test** your code and see if it is **doing** what it is **supposed** to do. In the case of **retrieving** `data` from an `Api`, it is important to check whether the `data` is **_indeed_** being **retrieved** **_early on_**.
- Next, I **set up** my `variables` I need inside the `parent function`.
- First I `declare` and `initialize` a `variable` called `body`:

```javascript
const body = document.querySelector("body");
```

This is actually **_not necessary_** for your application, unless you want it to be! I created it to use toward the **_conditions_** I set for `revealing` and `hiding` the `content` of the **Api** `data` **inside** a `wrapper div` with the class of `.wrapper`.

- **_Next_**, I `declare` and `initialize` a `variable` called `wrapper`:

```javascript
const wrapper = document.querySelector(".wrapper");
```

Here I query a `div` **element** with the class of `.wrapper`. Inside this `div` is where **all** the `data` from the `Free IP Geolocation API` and the `Geolocation Api` are **_rendered_** to the page. You will **_want_** to **add** a **similar tag** to your `index.html`. It is a **_good idea_** to **wrap** a `div` around the `data` so it sits nicely on the page. However, you **_don't_** **need** to `query` it **_here_**. Again, I `query` it here to use it toward `toggling` the `visibility` of the **Api** `data`.

- Then I `declare` and `initialize` a `variable` called `findMeHeading`.

```javascript
const findMeHeading = document.querySelector("#heading");
```

- After I `declare` and `initialize` the `variable`, I set the `.innerHTML` **property** on it.

```javascript
findMeHeading.innerHTML = `Hello <span>visitor</span>!<br/>
      Click on link below to find your location on <span>Open Street Maps</span>:`;
```

This is my **_greeting_** to my **visitors** when they land on the page.

- Now I `declare` and `initialize` a `variable` called `status`.

```javascript
const status = document.querySelector("#status");
```

I **_use_** this **variable** in both the `geoSuccess()` and the `error()` **inner** `functions` related to the `Geolocation Api`. We will get back to this variable in a bit.

- Next I `declare` and `initialize` a `variable` called `mapLink`.

```javascript
const mapLink = document.querySelector("#map-link");
```

- Then I set the `.href` property on the `mapLink` **element** and `assign` it a `value` of an empty `template literal`: `` . Remember from the `slide deck`, that the `#map-link` **id** is the `id` **name** set to an `anchor` **tag**.

```javascript
mapLink.href = ``;
```

Now I set the `.textContent` **property** on `mapLink` and `assign` it a `value` of an **_empty_** `template literal`.

```javascript
mapLink.textContent = ``;
```

I use `mapLink` in the `geoSuccess()` inner function. Inside the `geoSuccess()` **function**, `mapLink.href` will be set to an `OpenStreetMap` **link** that takes you to a `street map` **_obtained from_** the `longitude` and `latitude` **coordinates** retrieved from the `Geolocation Api`.

Now I `declare` and `initialize` a `variable` called `div` which I `query` by its class name `.center`, using `document.querySelector(".center")`.

```javascript
const div = document.querySelector(".center");
```

Then I set the `.innerHTML` **property** on `div` and `assign` it a `value` of a `template literal`, and I use `interpolation` (insertion) inside the `template literal` as well. This is where the `Free IP Geolocation API` is **_rendered_** on the page. The `data` is `interpolated` using the `ip` variable **_passed in_** as a `parameter` to the `parent function`, in my case `getGeoIP()`, in the `declaration` of the `function` which takes place at the **_top_** of the `main.js` file. I set **Api** `properties` on the **_interpolated_** `ip` **variable**.

```javascript
div.innerHTML = `
The <span>name</span> of the <span>country</span> you are hailing from is <span class="data">${ip["country_name"]}</span>.`;
```

Here, I am using `bracket notation` instead of `dot notation`.

I am **_only displaying_** **one property** here, because that is **_all_** that is **required** of you for **_this project_**. If you **_want_** to **display** **_more information_** by setting **_more properties_** on `ip`, go to town and have fun doing so! It really **_is_** **fun** to **_create code_** which **displays** `data` you are **_fetching_** with the `fetch()` **Api** from somewhere else.

- After `div.innerHTML` comes the **_first_** `inner function`,`geoSuccess(position)` function.

```javascript
function geoSuccess(position) {
  const latitude = position.coords.latitude;
  const longitude = position.coords.longitude;
  status.textContent = ``;
  mapLink.href = `https://www.openstreetmap.org/#map=18/${latitude}/${longitude}`;
  mapLink.textContent = `Your Coordinates are Latitude: ${latitude} ° and Longitude: ${longitude} °`;
}
```

- When the function is `declared`, a `parameter` called `position` is **_passed into_** **it** so that it is **readily available** to the `body` of the `function`. That way, I can **_immediately_** **use** it in the `value` of the **_newly_** `declared` and `initialized` **latitude** and **longitude** variables **_inside_** the `function`.
- I **_don't_** **set** a **message** inside the back ticks (`` ) of `status.textContent`, because this function is ***only triggered*** if the `Geolocation Api` is ***available*** in the `active browser window` (the ***current browser*** a user has open). I ***only*** **set** a **message** inside the back ticks ( ``) if the `GeoLocation Api` is **_not_** **available** in a user's `active browser window`.
- But since `geoSuccess` is only triggered when the `Geolocation Api` is available in a user's `active browser window`, I am able to **set** the `value` of `mapLink.ref` to the `OpenStreetMap` `url` to a page which contains a map of a user's location obtained from the `longitude` and `latitude` **coordinates** **_retrieved_** via the `Geolocation Api`.
- Lastly, I **set** a **message** to inform the user of their current position via longitude and latitude. Again, I use interpolation to insert a user's longitude and latitude dynamically. That's because it will not always be the same user who lands on my application page, so I have to set it dynamically with interpolation so that it always only provides the longitude and latitude of the current visitor on the site.

```javascript
mapLink.textContent = `Your Coordinates are Latitude: ${latitude} ° and Longitude: ${longitude} °`;
```

Just to **_recap_**, a **reference** to the `geoSuccess` **function** is **_passed_** into the **built-in** `Geolocation Api` **method** called `.getCurrentPosition()`, which is set to `navigator.geolocation` **property** **_inside_** the `else` **block** of the `if/else` statement following the **_second_** `inner function` named `error`.

- **_Next up_** is the **second** `inner function`, `error()`.

```javascript
function error() {
  status.textContent = `Geolocation is not supported by your browser`;
  console.log(`the status ${status}`);
}
```

All this `function` **_does_** is `render` a `message` to the `visitor` on the `page` letting them know that `Geolocation` is **_not supported_** by their (`active`) `browser window`. It is the **_second argument_** **passed in** to the `.getCurrentPosition()` **Geolocation Api** `built-in` method **set** on `navigator.geolocation` **_inside_** the `else` **block** of the `if/else` **statement** that follows. So if the `Geolocation Api` is **_not available_** in the **visitor's** `browser`, the `reference` to the `error` **function** \***_passed in_** to `navigator.geolocation.getCurrentPosition()` is `triggered`, and the **message** `Geolocation is not supported by your browser` **_appears_** on the **page** instead of **_nothing_**:

```javascript
status.textContent = ``;
```

- **_Next_** **comes** the `if/else statement` that **checks** for the `availability` of the `Geolocation Api` in an `active browser window`.

```javascript
if (!navigator.geolocation) {
  status.textContent = `Geolocation is not supported by your browser.`;
} else {
  status.textContent = `Locating...`;
  navigator.geolocation.getCurrentPosition(geoSuccess, error);
}
```

What the `if` statement in this `if/else statement` says is, if `.geolocation`, the `property` **_representing_** the `Geolocation Api`, which **_always_** has to be **set** to the `navigator` **object** which **holds information** about **_browsers_**, and **_specifically_** **here**, the `active browser window`, is NOT `available` in the `active browser window`, then the `value` of `status.textContent` should be printed out to the page for the visitor's edification. What the `else statement` says is, else (otherwise), the `value` of `status.textContent` should be `Locating...` until the `longitude` and `latitude` **coordinates** of the visitor's location are **_fully loaded_** on the **page**. And last of all in the else statement comes the crux of the Geolocation Api check:

```javascript
navigator.geolocation.getCurrentPosition(geoSuccess, error);
```

`getCurrentPosition(geoSuccess, error)` is the `function` that is being `called` **_regarding_** the `GeoLocation Api`. All the **_other_** code before it, `function geoSuccess()`, `function error()`, and the `if statement` of `if/else`, **all** are **set up** for

```javascript
navigator.geolocation.getCurrentPosition(geoSuccess, error);
```

- **_Last_** of all, we have the `.catch()` method. There, we **_pass_** in a **built-in** err object and then `console.log` it when an `error` **_occurs_** in the `body` of the `getGeoIP()` **function**. It is **_chained_** to the **second** `.then()` block. This is called when an `error` is **_returned_** from **somewhere** in the `body` of the `getGeoIP()` **function**. It is **_absolutely necessary_** to `chain` this to the **second** `then ()` **block** which **contains** **_almost all_** of the `code` inside `getGeoIP()`. And most important, it **contains** the **object** (`ip = geoIP`) containing the data passed to it from the `res` **object** **_retrieved_** from the `fetch(geoIpUrl)` **request** to the `Free IP Geolocation API`.

And that is it! So, your **JavaScript** `code` should **_end up_** looking something like this:

```javascript
const ul = document.getElementById("geoIp");
const geoIpUrl = `https://freegeoip.app/json/`;
function getGeoIP(ip) {
  fetch(geoIpUrl);
    .then(res => res.json())
    .then(geoIp => {
        ip = geoIp;
        console.log(ip.country_code);
        const findMeHeading = document.querySelector("#heading");
        findMeHeading.innerHTML = `Hello <span>visitor</span>!<br/>
      Click on link below to find your location on <span>Open Street Maps</span>:`;
        const status = document.querySelector("#status");
        const mapLink = document.querySelector("#map-link");
        mapLink.href = ``;
        mapLink.textContent = ``;
        const div = document.querySelector(".center");
        div.innerHTML = `
        The <span>name</span> of the <span>country</span> you are hailing from is <span class="data">${ip["country_name"]}</span>.`
function geoSuccess(position) {
        const latitude = position.coords.latitude;
        const longitude = position.coords.longitude;
        status.textContent = ``;
        mapLink.href = `https://www.openstreetmap.org/#map=18/${latitude}/${longitude}`;
        mapLink.textContent = `Your Coordinates are Latitude: ${latitude} ° and Longitude: ${longitude} °`;
      }
      function error() {
        status.textContent = `Geolocation is not supported by your browser`;
        console.log(`the status ${status}`);
      }
      if (!navigator.geolocation) {
        status.textContent = `Geolocation is not supported by your browser.`;
      } else {
        status.textContent = `Locating...`;
        navigator.geolocation.getCurrentPosition(geoSuccess, error);
      }
    })
    .catch(err => {
         console.log(err);
    });
}
```

- To **_check out_** what my `index.html` and my `main.css` look like, and the **whole project** in general, **_please visit_** the [geo-ip-app repository](https://github.com/interglobalmedia/geo-ip-app) on `Github`.

## Week 6 Homework Part 2

**Note**: As always, all the answers to the questions can be found on the slide deck associated with the week's content. In this case, it is the
[COMD3663 Dynamic Web 1 Using The Fetch Api With The Free Geo Ip Api](https://interglobalmedia.github.io/fetch-geo-ip-api/#/) slide deck.

1. What is the fetch Api? a. What does it replace the functionalities of? b. What does it provide an interface for?
2. What is a JavaScript Promise?
3. Why do developers like to use the fetch Api? And especially in conjunction with what? Give two reasons.
4. What is the fetch Api completely based on?
5. What is the function declaration syntax of a regular named function?
6. What is the first thing the declaration of regular named function begins with?
7. What is that first thing followed by?
8. What rules do function names follow?
9. What is promise chaining represented by in our Free IP Geolocation Api project?
10. Why do we use arrow functions inside of the .then() blocks?
11. What is the GoeLocation Api?
12. What must applications add to their application code in order to be able to use the Geolocation Api? There are two pieces involved. Explain what each piece represents.
13. How does the user allow the application to access their location? Use the application that you build to find out how.
14. If the Geolocation Api is available in the active browser window, what built-in Geolocation method do we use to get the location of the user by longitude and latitude coordinates?

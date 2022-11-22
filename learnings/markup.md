# Markup portfolio

## 1. Structure a site using semantic HTML to aid accessibility


``` html
    <header class="header justify-space-between">
        <img src="./images/pe-logo.png" alt="Purple Elephant logo">
        <a href="#" class="toggle-navbar">
            <span class="bar"></span>
            <span class="bar"></span>
            <span class="bar"></span>
        </a>
        <nav class="navbar-ctn">
            <ul class="navbar">
                <li><a class="link-underline-effect" href="#">Home</a></li>
                <li><a class="link-underline-effect" href="#about-us">About us</a></li>
                <li><a class="link-underline-effect" href="#portfolio">Portfolio</a></li>
                <li><a class="link-underline-effect" href="#meetteam">Meet the team</a></li>
                <li><a class="link-underline-effect" href="contact.html">Contact</a></li>
            </ul>
        </nav>
    </header>
```

```html
        <section class="about-us white-bg" id="about-us">
            <h3>About us</h3>
            <div class="flex-ctn-row about-us-ctn">
                <div class="about-us-message">
                    <p>Why choose the Purple Elephant?
                        Although this wonderful art is down to interpretation, we believe that the elephant symbolizes loyalty, resilience, and excellent attention to detail. Which is why joining us will lead you to great and extremely promising beginings.</p>
                </div>
                <img src="./images/elephant.png" alt="painting of a purple elephant" class="about-us-img">
            </div>
        </section>
```

``` html
    <footer class="flex-ctn-row">Made for the FAC26 Mark-Up Project</footer>

```

## 2. Make a web page more readable for screen readers

```html
      <label for="name" class="form-label">Name</label>
      <input type="text" id="name" name="firstname" placeholder="Your full name..." required>

      <label for="email" class="form-label">Email</label>
      <input type="text" id="email" name="email" placeholder="Your email..." required>

      <label for="companyname" class="form-label">Company name</label>
      <input type="text" id="companyname" name="companyname" placeholder="Your company name..." required>

```

## 3. Design a UI without relying solely on colour, so that we don’t exclude colour-blind users

https://fac26.github.io/thepurpleelephant/

## 4. Ensure our UI has sufficient colour contrast so that everyone can perceive it comfortably

![image](https://user-images.githubusercontent.com/104517597/203396363-a3fa265b-f99c-4eb6-9eb5-d40711248785.png)

## 5. Use various tools to check that a website meets accessibility criteria

We referred to [The A11y Project’s Checklist](https://www.a11yproject.com/checklist/)

We also used lighthouse to check accessibility. Our index.html is not as accessible, partly because of the image carousel having empty buttons, but our contact.html page looks pretty good!

![image](https://user-images.githubusercontent.com/104517597/203399551-b96f7285-59b4-43f8-9010-eda026a51642.png)


## 6. Ensure a website displays well on screens of different sizes

![image](https://user-images.githubusercontent.com/104517597/203396651-604db173-3357-469e-9f54-005d05f99df2.png)

![image](https://user-images.githubusercontent.com/104517597/203399098-18088496-d3bf-4d1c-9685-1a598fd392b5.png)

## 7. Use CSS media queries to ensure content is always presented effectively

``` css
@media all and (max-width: 600px){
    .about-us-img {
        display: none;
    }
}
```

``` css
@media all and (max-width: 550px){
    .image-carousel {
        max-width: 400px;
    }
    .images {
        width: calc(400px - 10px);
        height: calc(400px - 10px);
    }
}
@media all and (max-width: 420px){
    .image-carousel {
        max-width: 280px;
    }
    .images {
        width: calc(280px - 10px);
        height: calc(280px - 10px);
    }
}

```

## 8. Demonstrate a mobile-first approach to designing a website with a great user experience

We didn't use a mobile-first approach but we did try to make sure it was functional on mobile with media queries and adding a hamburger menu. See, for example, Issue [#24](https://github.com/fac26/thepurpleelephant/issues/24).

## 9. Create an attractive and accessible colour palette for a project

```css
:root {
    --purple: #80558C;
    --white: #FFF;
    --grey: #5b5b5b;
    --yellow: #e9c93a;
```

## 10. Use CSS variables to apply repeated colours to HTML elements

```css
.purple-bg {
    background: var(--purple);
}
.white-bg {
    background: var(--white);
}
```

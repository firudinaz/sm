
# Step-by-step Tutorial

### Project Structure:

    .
    ├── ...
    ├── css                    # website style files
    │   ├── bootstrap.min.css        
    │   ├── fontawesome-all.min.css        
    │   └── flaticon.css      
    │   ├── style.css       
    ├── font                   # (font-related files, if any)
    ├── img                    # images used in a website
    │   ├── favicon.png        
    │   └── logo-32.png      
    ├── JS                     # javascript files used in website
    │   ├── jquery-3.5.0.min.js       
    │   ├── bootstrap.min.js     
    │   └── imagesloaded.pkgd.min.js    
    │   ├── validator.min.js        
    │   └── main.js   
    ├── index.html             # this our index page (whole website)
    └── ...


## How to create the HTML using Bootstrap:
### Step 1: Set up the HTML Structure 
- Start by creating a new HTML document.
- Add the basic HTML structure with the **<!doctype html>**, **<html>**, and **<head>** tags.

### Step 2: Include Bootstrap and Other Resources
* Inside the **<head>** tag, include the necessary CSS files.
- We can visit **https://getbootstrap.com/docs/** and download the latest version of Bootstrap.
- Copy the **bootstrap.min.css** file from the downloaded Bootstrap package and save it in a folder called **"css"** in our project directory.
- Add the following code inside the **<head>** tag to include the Bootstrap CSS file: 

```html
<link rel="stylesheet" href="css/bootstrap.min.css">
```

Similarly, download the Fontawesome and Flaticon CSS files and save them in the **"css"** folder.
Add the following code inside the **<head>** tag to include the Fontawesome and Flaticon CSS files:
```html
<link rel="stylesheet" href="css/fontawesome-all.min.css">
<link rel="stylesheet" href="font/flaticon.css">
```
Next, include the Google Web Fonts. Add the following code inside the **<head>** tag:
```html
<link href="https://fonts.googleapis.com/css?family=Roboto:300,400,500,700&amp;display=swap" rel="stylesheet">
```

Finally, add a custom CSS file called **"style.css"** to the "css" folder and include it using the following code inside the **<head>** tag:

```html
<link rel="stylesheet" href="style.css">
```

## Step 3: Set Up the Body Content

- Inside the **body** tag, start by checking if the browser is outdated using a conditional comment. If the browser is outdated, display a message asking the user to upgrade.

```html
<!--[if lt IE 8]>
    <p class="browserupgrade">You are using an <strong>outdated</strong> browser. Please <a href="http://browsehappy.com/">upgrade your browser</a> to improve your experience.</p>
<![endif]-->
```

- Next, create a **div** with an **id** attribute set to **"preloader"** to display a preloader animation.
- Inside the preloader **<div>**, add three child **<div>** elements with classes **"line1"**, **"line2"**, and **"line3"** to represent the preloader animation.

```html
<div id="preloader" class="preloader">
    <div class='inner'>
        <div class='line1'></div>
        <div class='line2'></div>
        <div class='line3'></div>
    </div>
</div>
```
- Now, create a **section** element with classes **"fxt-template-animation"** and **"fxt-template-layout32"** to hold the main content of the page.
- Inside the section, create a **div** with the class **"fxt-content-wrap"** to wrap the logo, title, description, and button.
- Add an **<a>** tag with the class **"fxt-logo"** inside the content wrap **<div>**. Set the href attribute to **"#"**(this can be a website link) and add an **<img>** tag inside it to display the logo image.
```html
<a href="#" class="fxt-logo"><img src="img/logo-32.png" alt="Logo"></a>
```
- Add an **h1** tag with the class **"fxt-main-title"** to display the main title.

```html
<h1 class="fxt-main-title">Welcome!</h1>
```
- Add a **p** tag with the class **"fxt-main-description"** to display the main description.

```html
<p class="fxt-main-description">Dear customer. Please fill the form below.</p>
```
- Finally, create a **div** with the class **"fxt-btns-wrap"** to wrap the button.
- Inside the buttons wrap **<div>**, create a **<ul>** tag and add an **<li>** - tag inside it.
- Inside the **<li>** tag, create a **<button>** with the classes **"fxt-modal-btn"** and **"text-center"**. Set the type attribute to **"button"** and add **data-bs-toggle="modal"** and **data-bs-target="#logIn"** attributes to open the modal when clicked.

```html
<button type="button" class="fxt-modal-btn text-center" data-bs-toggle="modal" data-bs-target="#logIn">Click to fill the form</button>
```

### Step 4: Create the Modal Dialog and Form
- After the main content, create a modal dialog by adding a **div** with the classes **"modal fade"** and **"layout32"** outside the **<section>** tag. Set the id attribute to **"logIn"**.
- Inside the modal dialog **<div>**, add another **<div>** with the class **"modal-dialog"** and **"modal-dialog-centered"** to center the modal on the screen.
- Within the modal dialog **<div>**, create a **<div>** with the class **"modal-content"** to hold the modal's content.
- Inside the modal content **div**, add a close button using the **<button>** tag with the class **"fxt-btn-close"**. Set the type attribute to **"button"** and add **data-bs-dismiss="modal"** attribute to close the modal when clicked. Add a **<span>** tag with the aria-hidden attribute set to **"true"** and the inner HTML as **"X"** to display the close icon.

```html
<button type="button" class="fxt-btn-close" data-bs-dismiss="modal" aria-label="Close"><span aria-hidden="true">&times;</span></button>
```

- Next, add a **div** with the class **"fxt-page-title-wrap"** to hold the modal's page title.
- Inside the page title wrap **div**, add an **h2** tag with the class **"fxt-page-title"** to display the modal's page title.

```html
<h2 class="fxt-page-title">Application Form</h2>
```

- Now, create a  **div** with the class  **"fxt-form" ** to wrap the form elements.
- Inside the form  **div**, add a  **form** tag with the action attribute set to  **"https://webto.salesforce.com/servlet/servlet.WeoToCase?encoding=UTF=8"** and the method attribute set to **"POST"**. _**This will POST the inputs when customer fill to our salesforce_**
- This specifies the URL where the form data will be sent and the HTTP method to be used.

```html
<form action="https://webto.salesforce.com/servlet/servlet.WeoToCase?encoding=UTF=8" method="POST">

```
- Inside the form, create various form fields using **<input>**, **select**, and **textarea** tags. Customize the attributes as needed to suit your requirements.

- **For example, add an email field:**
```html
<input type="email" id="email" class="form-control" name="email" placeholder="Enter Email" required="required">
```

-Similarly, add a select field for priority:
```html
<select class="form-select" aria-label="Default select example">
    <option selected>Select Priority</option>
    <option value="1">Low</option>
    <option value="2">Medium</option>
    <option value="3">High</option>
</select>
```

- Continue adding other form fields as per your needs, such as text fields and textarea fields.
- Finally, add a submit button within the form using the **button** tag with the class **"fxt-btn-fill"** and the type attribute set to **"submit"**.

```html
<button type="submit" class="fxt-btn-fill">Submit</button>
```
### Step 5: Include JavaScript Files

- At the end of the **body** tag, add the necessary JavaScript files to enable the functionality of Bootstrap components.
- Download the jQuery library and save it in a folder called **js** in your project directory.
- Add the following code just before the closing **</body>** tag to include the jQuery and Bootstrap JavaScript files:
```html
<script src="js/jquery-3.5.0.min.js"></script>
<script src="js/bootstrap.min.js"></script>
```
- Additionally, you can include other JavaScript files such as Imagesloaded and Validator if you require their functionality.

That's it!
We have now created an HTML page with a Bootstrap-based form and a modal dialog. **We have to update the file paths for CSS and JavaScript files based on our project structure.** 
**We can further customize the styling and functionality as needed.**

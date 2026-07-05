# glpi-implementation-
glpi logo change of 10 versions 
**First go to location administrator->Entitys-> UI customaization ....then code is pasted here
**
/* ১. লগইন পেজের লোগো */
.login-box .logo-glpi, div#logo_login {
    background-image: url('http://119.148.35.59/logo/Logo.jpg') !important;
    background-size: contain !important;
    background-repeat: no-repeat !important;
    background-position: center !important;
    height: 80px;
    width: 100%;
}

/* ২. বাম পাশের সাইডবারের GLPI লোগো হাইড করার জন্য */
.logo-full, 
.logo-mini, 
.brand-text,
.sidebar-brand svg,
.sidebar-brand img {
    display: none !important;
}

/* ৩. সাইডবারে আপনার নতুন লোগোটি বসানোর জন্য */
.sidebar-brand, 
.brand-link, 
.navbar-brand {
    background-image: url('http://119.148.35.59/logo/Logo.jpg') !important;
    background-size: contain !important;
    background-repeat: no-repeat !important;
    background-position: left center !important;
    padding-left: 15px !important;
    min-height: 50px !important;
}

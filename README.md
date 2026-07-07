# glpi-implementation-
glpi logo change of 10 versions 
**First go to location administrator->Entitys-> UI customaization ....then code is pasted here
**
.login-box .logo-glpi, div#logo_login {
    background-image: url('http://192.168.1.66/logo/Logo.jpg') !important;
    background-size: contain !important;
    background-repeat: no-repeat !important;
    background-position: center !important;
    height: 80px;
    width: 100%;
}

.logo-full, 
.logo-mini, 
.brand-text,
.sidebar-brand svg,
.sidebar-brand img {
    display: none !important;
}

.sidebar-brand, 
.brand-link, 
.navbar-brand {
    background-image: url('http://192.168.1.66/logo/Logo.jpg') !important;
    background-size: contain !important;
    background-repeat: no-repeat !important;
    background-position: left center !important;
    padding-left: 15px !important;
    min-height: 50px !important;
}


database backup and restore command is here 
mysql -u glpi -p'your_pass' glpidb > data/glpi_data.sql (it's backup rule)
mysql -u glpi -p'your_pass' glpidb < data/glpi_data.sql (it's restore rule)


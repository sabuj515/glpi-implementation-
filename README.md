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

auto backup rule ----
step1: /data/backup    (create a directory )        
Step2:  vi glpi_autoback.sh
then paste the below line..

#!/bin/bash
BACKUP_DIR="data/glpi_backups"
DB_USER="glpi"
DB_PASS="Qatl@0751"
DB_NAME="glpidb"
DATE=$(date +%F_%H-%M-%S)
FILENAME="${BACKUP_DIR}/glpi_backup_${DATE}.sql"

mysqldump -u ${DB_USER} -p"${DB_PASS}" --no-tablespaces ${DB_NAME} > ${FILENAME}

if [ $? -eq 0 ]; then
    echo "[$(date)] Backup successfully created: ${FILENAME}" >> ${BACKUP_DIR}/backup_log.log
else
    echo "[$(date)] Backup FAILED!" >> ${BACKUP_DIR}/backup_log.log
fi

find ${BACKUP_DIR} -type f -name "*.sql" -mtime +30 -exec rm {} \;  (This execute the line deleted backup  After 30 days)  

Step3: chmod -x glpi_autoback.sh
step4: 0 2 */2 * * data/glpi_backups/glpi_autoback.sh >/dev/null 2>&1 
💡 এই টাইমিংটার মানে কী?
    0 2 = রাত ২:০০ টার সময় ব্যাকআপটি রান হবে (যখন সার্ভারে ইউজারদের চাপ কম থাকে)।
    */2 = প্রতি ২ দিন পর পর (Every 2 days)।
Done 



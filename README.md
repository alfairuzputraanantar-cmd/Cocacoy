# CocaCoy - Smart Inventory & Sales Management ERP

CocaCoy is a web-based ERP system designed to help businesses and small shops (UMKM) manage inventory, track product stocks, analyze daily revenue, and process transactions using a smart Cashier (POS) interface with barcode scanning.

This application is packaged using Docker and served using the *Nginx (Alpine Image)* web server. 

Key Features : 
- Business Dashboard: Displays real-time statistics, including inventory value, daily revenue, profit, and Low Stock Alerts.
- Smart Cashier (POS): Provides a fast checkout process through manual product selection or camera-based barcode scanning.
- Inventory & Product Management: Allows users to add, edit, and restock products, as well as create custom columns such as Expiry Date and Supplier.
- Transaction History & Analytics: Presents activity timelines and visual charts to help users monitor sales performance.
- Report Export: Enables users to export business summaries into PDF and Excel formats.

Prerequisites : 

Please make sure you have the following on your machine before running the app :
- Git
- Docker Desktop (make sure you start the Docker Engine)

Instructions to Run the App
1. Clone the Repository
Open your terminal/Power Shell and run the following command:

```bash
git clone https://github.com/alfairuzputraanantar-cmd/Cocacoy.git
cd Cocacoy
```
2. Build Docker Image
```bash
docker build -t group03/cocacoy:week6 .
```
3. Run the Container
```bash
docker run -d --name cocacoy-app -p 8081:80 group03/cocacoy:week6
```

Access & Verification
- Main Page: http://localhost:8081
- Login Page: http://localhost:8081/login

Logs & Cleanup
Check Container Status
```bash
docker ps
docker logs cocacoy-app
```

Stop & Remove Container
```bash
docker stop cocacoy-app
docker rm cocacoy-app
```

Troubleshooting Notes
- Routing: Uses custom nginx.conf (try_files) to prevent 404 errors on HTML pages.
- Port Conflict: Change host port mapping (e.g. -p 8082:80) if port 8081 is occupied.

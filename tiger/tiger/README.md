# Basic Flask App

This small repo demonstrates a proper file structure for a Flask app. The folders named *static* and *templates* are required.

**Routes** and **static files** are handled correctly in all `src` and `href` attributes in the template files.

The template file `base.html` is used as a shell by the other three HTML templates. This means they insert content into `base.html` according to Jinja2 template rules.

## Deployment

This application is deployed on AWS EC2. The following steps were taken to deploy the application:

1. Launched an EC2 instance with Ubuntu Server 24.04 LTS, and connected via EC2 instance connect.

2. Update and install required packages:

```
sudo apt update
sudo apt install python3-pip -y
sudo apt install python3.12-venv -y
```

3. Clone the repository and set up the environment:
```
git clone https://github.com/yourusername/your-repo.git
cd your-repo
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

4. Run the Flask application:
```
flask run --host=0.0.0.0 --port=8000
```

5. Ensure port 8000 is open in your security group settings.

Your app only runs in the foreground, and it will stop as soon as you close your SSH session.

Here is a way to make it run in the background on EC2:
6. nohup flask run --host=0.0.0.0 --port=5000 &



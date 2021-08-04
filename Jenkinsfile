pipeline {
    agent any 
    stages {
        stage('Build') { 
            steps {
                // 
				sh 'pip3 install -r requirements.txt'
            }
        }
        stage('Test') { 
            steps {
                // 
				sh 'python3 manage.py test'
            }
        }
    
		stage('Deploy to Stagin') { 
            steps {
                // 
				sh 'ssh -o StrictHostKeyChecking=no deployment-user@192.168.56.105 "source venv/bin/activate; \
				cd polling; \
				git pull origin master; \
				pip install -r requirements.txt --no-with-script-location; \
				deactivate; \
				sudo systemctl restart nginx; \
				sudo systemctl restart gunicorn "'
            }
        }

        stage('Deploy to Prod') { 
            steps {
                // 
				sh 'ssh -o StrictHostKeyChecking=no deployment-user@192.168.56.101 "source venv/bin/activate; \
				cd polling; \
				git pull origin master; \
				pip install -r requirements.txt --no-with-script-location; \
				deactivate; \
				sudo systemctl restart nginx; \
				sudo systemctl restart gunicorn "'
            }
        }
    }
}
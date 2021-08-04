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
        stage('Deploy') { 
            steps {
                // 
				sh 'ssh deployment-user@192.168.56.103 "source venv/bin/activate; \
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
pipeline{
	agent {
		label {
			label 'dev'
		}
	}
	environment{
	PATH ="/mnt/buildtool/apache-maven-3.8.6/bin:$PATH"
	}
	stages {
		stage ('git clone') {
			steps {
				dir ('/mnt/dockerwars/') {
				sh 'sudo rm -rf * '
				sh 'git clone https://github.com/vikasdarade/hello-world.git'
				}
			    dir ('/mnt/dockerwars/hello-world/'){
				sh 'mvn install'
				sh 'sudo cp webapp/target/webapp.war /mnt/dockerwars/'
			        
			    }
			
				
			}
		}
		stage ('creation of container'){
			steps {
				dir ('/mnt/docker') {
				sh 'sudo rm -rf *'
				sh 'sudo git clone https://github.com/vikasdarade/dockercompose.git'
				}
				dir ('/mnt/docker/dockercompose'){
				sh 'sudo docker-compose down'   
				
				
				sh 'sudo docker-compose up -d'
				    
				
				
				}
				}
		}
	
	
	
	}
}

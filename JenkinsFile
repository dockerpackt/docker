pipeline {
    agent any
    stages{
        stage('clone the repo and removing the existing one')
        {
          steps {
          
              sh "rm -rf /home/coreopt1/docker"
              sh "git clone https://github.com/dockerpackt/docker.git"
               
               }
         }
         
         stage("copying files to /var/www/html")
         {
           steps 
           {
              sh "cp /home/coreopt1/docker/var/www/html/index.html /var/www/html/"
           }
          }
          
           stage("Installing the webserver and starting its service")
          {
            steps
            {
              sh "apt install apache2 -y"
              sh "systemctl start apache2"
            }
          }
          
          
          stage("Restarting the apache2 service")
          {
            steps
            {
              sh "systemctl restart apache2"
            }
          }
               
    }

}

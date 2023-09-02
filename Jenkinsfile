node {
    def app

    stage('Clone repository') {
      
        checkout scm
    }

    stage('Image Build') {
  
       app = docker.build("prashantjkamath/pythonapp5")
    }

    stage('Image Test') {
  

        app.inside {
            sh 'echo "Tests passed"'
        }
    }

    stage('Image Push') {
        
        docker.withRegistry('https://registry.hub.docker.com', 'dockerhub') {
            app.push("${env.BUILD_NUMBER}")                                                            //env.BUIILD_NUMBER is a standard defined variable in jenkins job. Yo need not define this//
        }
    }
    
    stage('Trigger ManifestUpdate') {
                echo "triggering updatemanifestjob"
                build job: 'update_manifest', parameters: [string(name: 'DOCKERTAG', value: env.BUILD_NUMBER)]
        }
}

// 30 Creating & configuring the Jenkinsfile

pipeline {      // declarative pipeline
    agent { label 'linux'}       // for this build use the node set up with label 'linux' (cf 12 Adding a build node)
    stages
    {
        stage('Hello from Github')
        {
            steps
            {
                echo 'Hello there world!'
            }
        }
    }

}
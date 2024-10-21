pipeline {
    agent any
    parameters {
        choice(name: 'ENVIRONMENT', choices: ['Prod', 'Non Prod'], description: 'Pick environment')
    }

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World '
            }
        }
         stage('Prod') {
            when {
                expression { params.ENVIRONMENT == 'Prod' }
            }

            steps {
                input  message:"Should we continue?" , ok:"Yes, we should."
                echo 'This is for  Production'
            }
        }
         stage('NonProd') {
            when {
               expression { params.ENVIRONMENT == 'Non Prod' }
            }
            steps {
                echo 'This is for Non Production'
            }
        }

    }
}

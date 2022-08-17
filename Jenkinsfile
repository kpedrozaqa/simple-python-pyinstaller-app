pipeline{
    agent{label 'principal'}
    stages{
        stage('Checkout'){
            steps{
                git branch: 'master', url: 'https://github.com/kpedrozaqa/simple-python-pyinstaller-app.git'
            }
        }
        stage('Build'){  
            steps{
                sh 'python3 -m py_compile sources/add2vals.py sources/calc.py' 
                stash(name: 'compiled-results', includes: 'sources/*.py*')
            }
        }
        stage('Test'){
            steps{
                sh 'python3 sources/test_calc.py'
            }
        }
    }
}

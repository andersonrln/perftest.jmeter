pipeline {
  agent {
    kubernetes {
      label 'jmeter'
      containerTemplate {
        name 'jmeter'
        image 'justb4/jmeter'
        ttyEnabled true
        command 'cat'
      }
    }
  }
  stages {
    stage('Run performance test') {
      steps {
        container('jmeter') {
          sh 'jmeter -n -t performancetest-samu.jmx'
          // perfReport modeEvaluation: true, modeOfThreshold: true, sourceDataFiles: 'results_file.jtl'
        }
      }
    }
  }
}
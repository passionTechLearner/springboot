pipeline {
  agent any
  triggers {
    GenericTrigger(
     genericVariables: [
      [key: 'number', value: '$.number'],
      [key: 'action', regexpFilter: '[^a-z_-]', value: '$.action']
     ],
     causeString: 'Triggered on $ref',
     regexpFilterExpression: 'generic $ref',
     regexpFilterText: '$repository refs/heads/' + BRANCH_NAME,
     printContributedVariables: true,
     printPostContent: true
    )
  }
  stages {
    stage('Test Generic Trigger') {
      steps {
        sh """
          echo Variables from shell:
          echo number ${number}
          echo action ${action}
        """
      }
    }
  }
}

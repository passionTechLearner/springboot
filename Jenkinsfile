pipeline {
  agent any
  triggers {
    GenericTrigger(
     genericVariables: [
      [key: 'ref', value: '$.ref'],
      [key: 'repository', regexpFilter: '[^a-z_-]', value: '$.repository']
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
          echo reference ${ref}
          echo repository ${repository}
        """
      }
    }
  }
}

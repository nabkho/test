node {
  checkout scm
  timestamps {
//    stage('Validate Jobs') {
//      sh './gradlew build'
//    }
    if (env.BRANCH_NAME == 'main') {
      stage('Process Job DSLs') {
        jobDsl(
          failOnMissingPlugin: true,
          removedJobAction: 'DISABLE',
          removedViewAction: 'DELETE',
          targets: 'jobs/**/*.groovy'
        )
      }
    }
  }
}

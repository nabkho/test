node {
  checkout scm
  timestamps {
//    stage('Validate Jobs') {
//      sh './gradlew build'
//    }
    if (env.BRANCH_NAME == 'master') {
      stage('Process Job DSLs') {
        jobDsl(
          additionalClasspath: 'build/classes/main',
          failOnMissingPlugin: true,
          removedJobAction: 'DISABLE',
          removedViewAction: 'DELETE',
          targets: 'jobs/**/*.groovy'
        )
      }
    }
  }
}

#!/usr/bin/env groovy
// Groovy Language

def sendBuildStatus(status, message) {
  step([
    $class: 'GitHubCommitStatusSetter',
    contextSource: [
      $class: 'ManuallyEnteredCommitContextSource',
      context: 'JenkinsStaging'
    ],
    statusResultSource: [
      $class: 'ConditionalStatusResultSource',
      results: [[
        $class: 'AnyBuildResult',
        message: message,
        state: status
      ]]
    ]
  ])
}

if (env.BRANCH_NAME == 'master') {
  node {
echo "master"
  }
} else {
  node {
echo "pr"
  }
}

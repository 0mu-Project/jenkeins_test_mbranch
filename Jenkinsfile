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

if (env.CHANGE_ID != null) {
  node {
echo "pr"
    echo "Deployed to production"
  }
} else {
  node {
echo "pr"
  }
}
}

## gitlab-ci.yml
```yml
build-job:
  stage: build
  script:
    - echo "Hello, $GITLAB_USER_LOGIN!"
test-job1:
  stage: test
  script:
    - echo "This job tests something"
test-job2:
  stage: test
  script:
    - echo "This job tests something, but takes more time than test-job1."
    - echo "After the echo commands complete, it runs the sleep command for 20 seconds"
    - echo "which simulates a test that runs 20 seconds longer than test-job1"
    - sleep 10

pages:
  script:
    - mkdir .public
    - cp -r * .public
    - mv .public public
  artifacts:
    paths:
      - public

deploy-prod:
  stage: deploy
  script:
    - echo "This job deploys something from the $CI_COMMIT_BRANCH branch."

  environment: production
```

---

## **Thanks For Visiting**

<img src="https://i.gifer.com/origin/85/85a25f50ae5f4939336831d0b902e822_w200.gif" width=130 align=right>

Hope you liked it. Want to help?

- **[Star This Repository](https://github.com/clydebustamante/gitlab-ci)**

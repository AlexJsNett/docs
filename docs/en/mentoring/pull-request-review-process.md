## Task Checking Process by Mentor

1. A student completes an assignment in a school's private repository (unless otherwise specified in a task description).
2. The student creates and submits a Pull Request before the deadline.
   - The PR rules are specified [below](#pull-request-description-must-contain-the-following)
   - Penalties for deadline violations are listed [below](#deadlines-for-students)
3. Until the final grade is given by the mentor, the student can continue to implement remaining features
4. The mentor checks the PR, leaves his comments and recommendations on the quality of the code (copy-paste, magic numbers, project structure, etc.) and the implemented functionality. Leaves a comment with a preliminary score.
   - The score is set by the mentor based on the assessment criteria specified for each task
   - When giving a score, all implemented functionality must be taken into account. E.g. a student did not 100% fulfill the minimum (basic) requirements, but fulfilled some of the additional ones - all requirements must be taken into account
   - The mentor can set a preliminary score in advance, taking into account that the student will correct all the comments afterwards
5. The student addresses the comments within 5 days.
   - If the mentor's comment to the PR is pending the student's answer - the student writes the answer as a comment's reply
   - If the student has committed some changes, the student must leave a comment about what exactly has changed
6. Based on the results of the code review and corresponding changes, the mentor sets the final grade in Score (`RS APP > Submit-review`).
   - It is up to the mentor to decide whether to deduct points or not for the functionality implemented by the student after the deadline.
   - If the student has not addressed the mentor's comments, the mentor may further reduce the mark. The size of the penalty is at the discretion of the mentor, maximum -50 points.

## Pull Request Requirements (PR)

Pull Request is a place to discuss contributor's code. It should not be a monologue but rather a fruitful collaboration between a contributor and a reviewer. Stay professional, respect each other's time and efforts.

### Pull Request must not contain the following:

- Commented code
- Leftover and/or irrelevant files, auto-generated code, node_modules, etc.

### Pull Request description must contain the following:

1. Task URL.
2. Screenshot showing the result of Task's completion. The screenshot is added to a Pull Request as an image attachment. To achieve that you can just drag-and-drop the screenshot to the Description text area.
3. Deployment URL of your application. For frontend - Website URL, for backend - API Endpoint URL. To create deployment you can use the following:
   - gh-pages (if you have access to a private RS School repo)
   - web hosting, like [netlify.com](https://app.netlify.com/drop) (if you don't have access to a private RS School repo or can't deploy to `gh-pages` because of permissions)
   - other static assets storage with web serving capabilities, like [S3](https://docs.aws.amazon.com/AmazonS3/latest/userguide/WebsiteHosting.html)
   - serverless or self-hosted solutions for your API (make sure URL is public and accessible by other people)
   - naming scheme: GitHub account name - Task name.
4. Submission Date / Deadline Date.
5. Your self-check of Task's completion result and opinion on the achieved Score.

### Description Example

```
1. Task: https://github.com/rolling-scopes-school/tasks/blob/master/tasks/fancy-weather.md
2. Screenshot:
   ![](https://raw.githubusercontent.com/rolling-scopes-school/docs/master/docs/images/fancy-weather.png)
3. Deployment: https://chakapega-fancy-weather.netlify.com/
4. Done 28.05.2020 / deadline 31.05.2020
5. Score: 220 / 300
- Markup, design, UI (15/30)
  - [x] minimum page width at which it is displayed correctly – 320 рх (10)
  - [±] application's appearancecorresponds to the layout and/or its improved version (5/10)
  - [ ] aaplication works and looks correctly with any language (0)
- Section "Today's weather" displays the following data (15/20)
  - [x] use weather data and location (10)
  - [±] clock, refreshed each second (5/10)
 ...
```

## Code Review Process Recommendations

For a more efficient process of code review of student PRs, it is recommended to conduct it in 2 stages:

- Review of the "Draft" version of the task. The student creates a PR when the "Draft" version is ready, which shows the main concept of the task and implements the main parts of the application. This version may not cover additional requirements.
- Review of the "Release" version of the task. This is a completed and refactored version of the task, which contains all the changes addressing the comments and suggestions mentioned during the review of the "Draft" version.

This approach solves several problems that are usually encountered when reviewing and implementing large tasks:

- Reducing the one-time review load on the mentor.
  - It is often quite difficult to carefully look into the entire code of the task in one go and clarify all the concepts that the student missed within the large code base.
  - It is often much easier to find time for 2 smaller reviews, although in general, the total time may be increased.
- Catching architectural mishaps at the very beginning, which lead to "expensive", in terms of refactoring, problems
- Learn how to work with Git and GitHub
- Motivation to meet the deadline

## Code Review Process Example

1. **PR preparation check** - PR description, commits, and deployment.

- [Commit Requirements](https://rs.school/docs/git-convention)
- [Pull Request Requirements](#pull-request-requirements-pr)

After checking the PR description, commit names, and commit history, clone the student's repository and install the dependencies.

2. **Basic checks** - linter, tests, and build.

- If the task requires a linter or tests, the corresponding scripts are configured and all required checks pass
- Lint rules are not disabled without a clear reason; discuss whether each exception is necessary
- The project builds and runs without errors
- There are no `console.log` statements in production code
- There is no commented-out code

3. **Functionality check** - application behavior.

- All core features work correctly
- There are no errors in the console
- Requests are processed correctly
- The implemented functionality matches the task requirements

4. **Code review** - code quality and architecture.

Use the [mentor-resources reference](https://github.com/HelgaZhizhka/mentor-resources/blob/master/clean-code/index.md) for explanations and examples of clean code practices (available in Russian).

5. **UI/UX check** - design and user experience.

- The application matches the provided design, if any
- The layout is responsive, if required
- Clickable elements are visually distinguishable
- Interactive elements provide feedback, such as hover and active states

The [clean code checklist](https://github.com/HelgaZhizhka/mentor-resources/blob/master/clean-code/Check-List.md) can be used for self-checking and discussing code quality (available in Russian).

### Deadlines for Students

- Deadlines for all tasks are indicated in the course schedule.
- If student did not have time to turn in the assignment on time, mentor, at his own discretion, can apply the following penalties:
  - -10 score points if you are late up to 3 days, inclusive
  - -30% score percentage if you are late up to 7 days, inclusive
  - -70% score percentage if more than a week late
  - penalties can be omitted if there is a good reason (hospital, army training, etc.)
  - rounding occurs in favor of the student, when applying penalty coefficients

### Deadlines for Mentors

Mentor is expected to review student's work within one or two weeks of the student's submission. But the sooner the better. Deadline dates for students are indicated in the schedule.

## Recommended Links

- [Pull Request Requirements](#pull-request-requirements-pr)
- [Commit Requirements](https://rs.school/docs/git-convention)
- [Clean Code Practices - all materials](https://github.com/HelgaZhizhka/mentor-resources/blob/master/clean-code/index.md) (in Russian)
- [Clean Code Checklist](https://github.com/HelgaZhizhka/mentor-resources/blob/master/clean-code/Check-List.md) (in Russian)

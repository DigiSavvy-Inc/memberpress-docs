# How To Add MemberPress Quizzes to Courses

## Additional menu

[](https://memberpress.com/)MemberPress

The All-In-One WordPress Membership Plugin

 

![worker bees](https://memberpress.com/wp-content/themes/memberpress-theme/images/memberpress-logo-color.svg)

				Get MemberPress today! Start getting paid for the content you create!

[Get MemberPress Now](https://memberpress.com/plans/pricing/)

Search For

Search

# How To Add MemberPress Quizzes to Courses

Similar to adding lessons or assignments, you can add unlimited MemberPress quizzes to any MemberPress course.

This document will show you how to design MemberPress quizzes, add them to your courses, and manage them.

Note: MemberPress Course Quizzes add-on is available to MemberPress Plus and Pro plan members. If you're subscribed to the Basic plan, you can upgrade to the Plus or Pro plan. To upgrade, click the Change Plan link on your account page.

## Designing MemberPress Quizzes

MemberPress Quiz editor is (Gutenberg) block-based. This means you can design quizzes according to your needs like any other WordPress post.

Also, quizzes come with a separate MemberPress quiz block for each question type:

Therefore, within the quiz editor, you can design quizzes by combining any Gutenberg block with the MemberPress quiz question blocks:

![MemberPress quiz blocks](data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIzMDAiIGhlaWdodD0iMTUzIj48ZyBmaWx0ZXI9ImJsdXIoMTJweCkiPjxyZWN0IHdpZHRoPSIyMDAlIiBoZWlnaHQ9IjIwMCUiIHg9Ii01MCUiIHk9Ii01MCUiIGZpbGw9IiM0YzRjNGMiLz48cmVjdCB3aWR0aD0iMTAwJSIgaGVpZ2h0PSIxMDAlIiBmaWxsPSIjNGM0YzRjIi8+PGcgZmlsbD0iI2ZmZiIgZmlsbC1vcGFjaXR5PSIuNSIgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoLjYgLjYpc2NhbGUoMS4xNzE4OCkiPjxjaXJjbGUgY3g9IjEyOSIgY3k9Ijc2IiByPSIxNTUiLz48Y2lyY2xlIGN4PSIxMjgiIGN5PSI4MCIgcj0iMTUzIi8+PGNpcmNsZSByPSIxIiB0cmFuc2Zvcm09Im1hdHJpeCgtMTc5LjIwNzQ2IDEyLjQwMTYyIC03LjU2OTMgLTEwOS4zNzg4NSAxMjQuNSA3NC40KSIvPjxjaXJjbGUgcj0iMSIgdHJhbnNmb3JtPSJyb3RhdGUoLTEwMi4xIDEwNC44IC0yNS4yKXNjYWxlKDEyMy45NTE1IDE2OC4wNzQzKSIvPjwvZz48L2c+PC9zdmc+)
Note: MemberPress quiz blocks are available only within the Quiz editor. Thus, these blocks will not be available on your lessons, courses, or any other WordPress post.

### Quiz Completion Settings

Each MemberPress quiz comes with additional post settings inside the Quiz editor, including the quiz completion settings. You can use these settings to define the criteria students must meet to complete the quiz.

Here, you can set any question as required, set the minimum passing score, and allow retakes.

#### Required Questions

When you set a question as required, it prevents students from skipping it. Therefore, students won’t be able to submit the quiz without answering all required questions:

![MemberPress Quizzes - Required Questions](data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIzMDAiIGhlaWdodD0iMTUzIj48ZyBmaWx0ZXI9ImJsdXIoMTJweCkiPjxyZWN0IHdpZHRoPSIyMDAlIiBoZWlnaHQ9IjIwMCUiIHg9Ii01MCUiIHk9Ii01MCUiIGZpbGw9Im11dGVkIi8+PHJlY3Qgd2lkdGg9IjEwMCUiIGhlaWdodD0iMTAwJSIvPjxnIGZpbGw9IiNmZmYiIGZpbGwtb3BhY2l0eT0iLjUiIHRyYW5zZm9ybT0idHJhbnNsYXRlKC42IC42KXNjYWxlKDEuMTcxODgpIj48Y2lyY2xlIHI9IjEiIHRyYW5zZm9ybT0ibWF0cml4KDE2NS4zMzgyOCAuODY1NzIgLS42NTYyIDEyNS4zMjQ2MiAxMzAuOCA1OS4zKSIvPjxjaXJjbGUgY3g9IjEyNyIgY3k9IjY5IiByPSIxNTMiLz48Y2lyY2xlIGN4PSIxNDIiIGN5PSIxMTAiIHI9IjE4NCIvPjxjaXJjbGUgY3g9IjEzNyIgY3k9IjQzIiByPSIxNjUiLz48L2c+PC9nPjwvc3ZnPg==)![MemberPress Quizzes - Required Questions](https://memberpress.com/wp-content/uploads/2024/04/mpcs-required-quiz-question.png)

When students try submitting the quiz without answering the required questions, MemberPress will display a message indicating questions needing answers.

![Required Questions Message](data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIzMDAiIGhlaWdodD0iMTUzIj48ZyBmaWx0ZXI9ImJsdXIoMTJweCkiPjxyZWN0IHdpZHRoPSIyMDAlIiBoZWlnaHQ9IjIwMCUiIHg9Ii01MCUiIHk9Ii01MCUiIGZpbGw9IiM5MDA4NGMiLz48cmVjdCB3aWR0aD0iMTAwJSIgaGVpZ2h0PSIxMDAlIiBmaWxsPSIjOTAwODRjIi8+PGcgZmlsbD0iI2ZmZiIgZmlsbC1vcGFjaXR5PSIuNSIgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoLjYgLjYpc2NhbGUoMS4xNzE4OCkiPjxjaXJjbGUgY3g9IjEyMyIgY3k9Ijc3IiByPSIxNjEiLz48Y2lyY2xlIHI9IjEiIHRyYW5zZm9ybT0ibWF0cml4KC0xNjAuOTE1MjQgMzEuMTgxNTUgLTMwLjAyMDggLTE1NC45MjUxIDE0MS43IDc4LjEpIi8+PGNpcmNsZSByPSIxIiB0cmFuc2Zvcm09Im1hdHJpeCgtMjI5Ljc4NDE3IDc0LjIxODI3IC00MS43NzM2OSAtMTI5LjMzMzgzIDEyNi41IDEzMCkiLz48Y2lyY2xlIHI9IjEiIHRyYW5zZm9ybT0icm90YXRlKC05Ni40IDEyMC4zIC0yOC4zKXNjYWxlKDU4LjkwMDY1IDE3Mi4zNTQ3MykiLz48L2c+PC9nPjwvc3ZnPg==)![Required Questions Message](https://memberpress.com/wp-content/uploads/2024/04/mpcs-required-message-1024x527.png)
#### Require Passing Score

If you plan on using quizzes to test your students' knowledge, you might want to set the quiz passing score.

To set the minimal passing score for a specific quiz, please follow these steps:

![MemberPress Quizzes - Require Passing Score](data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIzMDAiIGhlaWdodD0iMTUzIj48ZyBmaWx0ZXI9ImJsdXIoMTJweCkiPjxyZWN0IHdpZHRoPSIyMDAlIiBoZWlnaHQ9IjIwMCUiIHg9Ii01MCUiIHk9Ii01MCUiIGZpbGw9Im11dGVkIi8+PHJlY3Qgd2lkdGg9IjEwMCUiIGhlaWdodD0iMTAwJSIvPjxnIGZpbGw9IiNmZmYiIGZpbGwtb3BhY2l0eT0iLjUiIHRyYW5zZm9ybT0idHJhbnNsYXRlKC42IC42KXNjYWxlKDEuMTcxODgpIj48Y2lyY2xlIHI9IjEiIHRyYW5zZm9ybT0ibWF0cml4KDI1LjEwMjc2IDEzMC4zNTY3OCAtMTY3LjEzOTYgMzIuMTg2MDEgMTIxLjIgNjIpIi8+PGNpcmNsZSBjeD0iMTM2IiBjeT0iODYiIHI9IjE2OCIvPjxjaXJjbGUgcj0iMSIgdHJhbnNmb3JtPSJyb3RhdGUoODkuMiAxNy4yIDkxLjIpc2NhbGUoMTI3LjUxNTQ2IDIwMy41MjQ5NCkiLz48Y2lyY2xlIHI9IjEiIHRyYW5zZm9ybT0ibWF0cml4KC0xNTUuNTAxMzIgOS43ODMzMSAtOC4yNjE0NCAtMTMxLjMxMTkgMTIzLjMgNjYuMykiLz48L2c+PC9nPjwvc3ZnPg==)![MemberPress Quizzes - Require Passing Score](https://memberpress.com/wp-content/uploads/2024/04/mpcs-passing-score.png)

Note: Enabling the Require Passing Score will enable the Require Previous Lesson/Quiz option in the course settings.

Note: If the Show Question Answers option is enabled in your course settings, the answers will not be shown if the user fails the quiz.

#### Allow Retakes

When a student submits answers to a quiz, this is stored in MemberPress as a quiz attempt. By default, students are allowed only one quiz attempt for every quiz.

Therefore, in cases where a passing score is set, failing students will be blocked from progressing to the next step.

Note: MemberPress stores only one quiz attempt for each student.

You can change this by allowing retakes for the quiz:

![MemberPress Quizzes - Allow Retakes](data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIzMDAiIGhlaWdodD0iMTUzIj48ZyBmaWx0ZXI9ImJsdXIoMTJweCkiPjxyZWN0IHdpZHRoPSIyMDAlIiBoZWlnaHQ9IjIwMCUiIHg9Ii01MCUiIHk9Ii01MCUiIGZpbGw9Im11dGVkIi8+PHJlY3Qgd2lkdGg9IjEwMCUiIGhlaWdodD0iMTAwJSIvPjxnIGZpbGw9IiNmZmYiIGZpbGwtb3BhY2l0eT0iLjUiIHRyYW5zZm9ybT0idHJhbnNsYXRlKC42IC42KXNjYWxlKDEuMTcxODgpIj48Y2lyY2xlIGN4PSIxMzAiIGN5PSI3NCIgcj0iMTUyIi8+PGNpcmNsZSBjeD0iMTM1IiBjeT0iNDQiIHI9IjE3OSIvPjxjaXJjbGUgY3g9IjExNSIgY3k9IjY0IiByPSIxNzgiLz48Y2lyY2xlIGN4PSIxMTIiIGN5PSI4OCIgcj0iMTc5Ii8+PC9nPjwvZz48L3N2Zz4=)![MemberPress Quizzes - Allow Retakes](https://memberpress.com/wp-content/uploads/2024/04/mpcs-allow-retakes.png)

With retakes enabled, students will be able to retake the failed quiz. If a student reaches the retake limit without a passing score, the student will be blocked. To unblock the student, you will need to reset the student’s quiz attempts.

## Add MemberPress Quizzes to Courses

MemberPress Quizzes can be added to courses through the Course Curriculum. Here, you need to add your quiz to a course section and then add the quiz content:

![Adding MemberPress Quizzes](data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIzMDAiIGhlaWdodD0iMTU0Ij48ZyBmaWx0ZXI9ImJsdXIoMTJweCkiPjxyZWN0IHdpZHRoPSIyMDAlIiBoZWlnaHQ9IjIwMCUiIHg9Ii01MCUiIHk9Ii01MCUiIGZpbGw9IiM0YzRjNGMiLz48cmVjdCB3aWR0aD0iMTAwJSIgaGVpZ2h0PSIxMDAlIiBmaWxsPSIjNGM0YzRjIi8+PGcgZmlsbD0iI2ZmZiIgZmlsbC1vcGFjaXR5PSIuNSIgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoLjYgLjYpc2NhbGUoMS4xNzE4OCkiPjxjaXJjbGUgcj0iMSIgdHJhbnNmb3JtPSJyb3RhdGUoODAuMiAzLjUgMTA3KXNjYWxlKDEyMi4yMjU3MSAxODMuNDU5MDIpIi8+PGNpcmNsZSBjeD0iMTI3IiBjeT0iODIiIHI9IjE1NyIvPjxjaXJjbGUgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMTM4LjYyOTM2IDU4LjYxODkgLTczLjUzOTY1IDE3My45MTU4MSAxMzMuOCA3MC44KSIvPjxjaXJjbGUgY3g9IjE0NSIgY3k9IjEyMSIgcj0iMTcyIi8+PC9nPjwvZz48L3N2Zz4=)![Adding MemberPress Quizzes](https://memberpress.com/wp-content/uploads/2024/04/mpcs-add-quiz.png)

![Adding a Quiz Name](data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNTQxIiBoZWlnaHQ9IjEzMTYiIHZpZXdCb3g9IjAgMCAyNTQxIDEzMTYiPjxyZWN0IHdpZHRoPSIxMDAlIiBoZWlnaHQ9IjEwMCUiIHN0eWxlPSJmaWxsOiNjZmQ0ZGI7ZmlsbC1vcGFjaXR5OiAwLjE7Ii8+PC9zdmc+)![Adding a Quiz Name](https://memberpress.com/wp-content/uploads/2024/04/mpcs-quiz-name.png)

![Editing a Quiz](data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNTQyIiBoZWlnaHQ9IjEzMTYiIHZpZXdCb3g9IjAgMCAyNTQyIDEzMTYiPjxyZWN0IHdpZHRoPSIxMDAlIiBoZWlnaHQ9IjEwMCUiIHN0eWxlPSJmaWxsOiNjZmQ0ZGI7ZmlsbC1vcGFjaXR5OiAwLjE7Ii8+PC9zdmc+)![Editing a Quiz](https://memberpress.com/wp-content/uploads/2024/04/mpcs-edit-quiz.png)

Note: Each MemberPress quiz block will come with additional block-specific settings.

Was this article helpful?

[Yes](https://memberpress.com)
[No](https://memberpress.com)

### Related Articles

### Need Support?

Can't find the answer you're looking for?[Contact Support](https://memberpress.com)### Contents

 

### Helpful Articles

 

 

![computer girl](data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSI0MDkiIGhlaWdodD0iMzY0IiB2aWV3Qm94PSIwIDAgNDA5IDM2NCI+PHJlY3Qgd2lkdGg9IjEwMCUiIGhlaWdodD0iMTAwJSIgc3R5bGU9ImZpbGw6I2NmZDRkYjtmaWxsLW9wYWNpdHk6IDAuMTsiLz48L3N2Zz4=)![computer girl](https://memberpress.com/wp-content/themes/memberpress-theme/images/FooterCTAgirl.webp)

### Get MemberPress today!

Start getting paid for the content you create.

[Get MemberPress Now](https://memberpress.com/plans/pricing/)

      Recommended by top influencers and web hosts
			

![4.8 out of 5 on Capterra](data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIzMDAiIGhlaWdodD0iMjEwIj48ZyBmaWx0ZXI9ImJsdXIoMTJweCkiPjxyZWN0IHdpZHRoPSIyMDAlIiBoZWlnaHQ9IjIwMCUiIHg9Ii01MCUiIHk9Ii01MCUiIGZpbGw9IiM5NGE0NWMiLz48cmVjdCB3aWR0aD0iMTAwJSIgaGVpZ2h0PSIxMDAlIiBmaWxsPSIjOTRhNDVjIi8+PGcgZmlsbC1vcGFjaXR5PSIuNSIgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoLjYgLjYpc2NhbGUoMS4xNzE4OCkiPjxlbGxpcHNlIGN4PSIxMzQiIGN5PSIxNDgiIGZpbGw9IiNmZmZjZDkiIHJ4PSI4MCIgcnk9IjEyNiIvPjxjaXJjbGUgcj0iMSIgZmlsbD0iIzAzMDAwMCIgdHJhbnNmb3JtPSJtYXRyaXgoMjQuNTY5OTkgLS41ODYxOSA0LjQ3NDggMTg3LjU2MDMgMTYgMTQ0LjIpIi8+PGNpcmNsZSByPSIxIiB0cmFuc2Zvcm09Im1hdHJpeCgtMy43MzgxNyAtMjE3LjUwODcgMjAuMTExMDUgLS4zNDU2MyAyNDEuNSAuMSkiLz48Y2lyY2xlIHI9IjEiIGZpbGw9IiNmZmYiIHRyYW5zZm9ybT0icm90YXRlKC0xNzcuNCA3Mi4zIDgxLjYpc2NhbGUoODEuMTk1OTQgMzMuMjkxNzMpIi8+PC9nPjwvZz48L3N2Zz4=)![4.8 out of 5 on Capterra](https://memberpress.com/wp-content/themes/memberpress-theme/images/capterra-footer.png)

![4.7 out of 5 on G2](data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIzMDAiIGhlaWdodD0iMjEwIj48ZyBmaWx0ZXI9ImJsdXIoMTJweCkiPjxyZWN0IHdpZHRoPSIyMDAlIiBoZWlnaHQ9IjIwMCUiIHg9Ii01MCUiIHk9Ii01MCUiIGZpbGw9IiM4Yzk0NTQiLz48cmVjdCB3aWR0aD0iMTAwJSIgaGVpZ2h0PSIxMDAlIiBmaWxsPSIjOGM5NDU0Ii8+PGcgZmlsbC1vcGFjaXR5PSIuNSIgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoLjYgLjYpc2NhbGUoMS4xNzE4OCkiPjxjaXJjbGUgcj0iMSIgZmlsbD0iIzI5MDAwMCIgdHJhbnNmb3JtPSJtYXRyaXgoMS4zODYxNyA1OS4yMTI2MyAtMjU0LjkzMDE1IDUuOTY3OTQgMTUwLjggMjQuMykiLz48Y2lyY2xlIHI9IjEiIGZpbGw9IiNmZmYiIHRyYW5zZm9ybT0ibWF0cml4KDc5LjIxODc1IC0xMy40NDQ0NyAxMC40NjY2MyA2MS42NzI0NiAxMTguNyAxNjUuNykiLz48Y2lyY2xlIHI9IjEiIHRyYW5zZm9ybT0icm90YXRlKC0xMS45IDI4OS4zIC0xMDU0Ljkpc2NhbGUoNDMuMTQxMjQgMjU1KSIvPjxlbGxpcHNlIGN4PSIxMjUiIGN5PSI5NCIgZmlsbD0iI2ZmODkwNiIgcng9IjEwMSIgcnk9IjQzIi8+PC9nPjwvZz48L3N2Zz4=)![4.7 out of 5 on G2](https://memberpress.com/wp-content/themes/memberpress-theme/images/g2-footer.png)

![4.8 out of 5 on Trust Pilot](data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIzMDAiIGhlaWdodD0iMjEwIj48ZyBmaWx0ZXI9ImJsdXIoMTJweCkiPjxyZWN0IHdpZHRoPSIyMDAlIiBoZWlnaHQ9IjIwMCUiIHg9Ii01MCUiIHk9Ii01MCUiIGZpbGw9IiM3NjdkNmEiLz48cmVjdCB3aWR0aD0iMTAwJSIgaGVpZ2h0PSIxMDAlIiBmaWxsPSIjNzY3ZDZhIi8+PGcgZmlsbC1vcGFjaXR5PSIuNSIgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoLjYgLjYpc2NhbGUoMS4xNzE4OCkiPjxjaXJjbGUgcj0iMSIgZmlsbD0iI2ZmZmZiOSIgdHJhbnNmb3JtPSJyb3RhdGUoLTE3NS44IDcxLjUgNjMuNSlzY2FsZSg4NC41MzUwMSAxMDcuNzM1NDEpIi8+PGNpcmNsZSByPSIxIiBmaWxsPSIjMDAxMjAwIiB0cmFuc2Zvcm09Im1hdHJpeCgzNi4zOTA1MyAxLjg2MzEgLTEyLjk4ODY3IDI1My42OTc1NCAxMiAzNi42KSIvPjxlbGxpcHNlIGN4PSIxMzgiIGN5PSIxNzAiIGZpbGw9IiNmZmYiIHJ4PSI4NCIgcnk9IjQyIi8+PGNpcmNsZSByPSIxIiB0cmFuc2Zvcm09InJvdGF0ZSgtMy43IDE0MDQuOCAtMzk1My42KXNjYWxlKDI4LjE3Mjk1IDIzOC44NTEzNCkiLz48L2c+PC9nPjwvc3ZnPg==)![4.8 out of 5 on Trust Pilot](https://memberpress.com/wp-content/themes/memberpress-theme/images/trustpilot-footer.png)

[](https://www.wpbeginner.com/plugins/5-best-wordpress-membership-plugins-compared/)

![Easiest Admin - Summer 2024](data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyOTkiIGhlaWdodD0iMzg5Ij48ZyBmaWx0ZXI9ImJsdXIoMTJweCkiPjxyZWN0IHdpZHRoPSIyMDAlIiBoZWlnaHQ9IjIwMCUiIHg9Ii01MCUiIHk9Ii01MCUiIGZpbGw9IiM4ODgiLz48cmVjdCB3aWR0aD0iMTAwJSIgaGVpZ2h0PSIxMDAlIiBmaWxsPSIjODg4Ii8+PGcgZmlsbC1vcGFjaXR5PSIuNSIgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoLjggLjgpc2NhbGUoMS41MTk1MykiPjxlbGxpcHNlIGN4PSI5NCIgY3k9IjcyIiBmaWxsPSIjZmZmZmVjIiByeD0iMTI3IiByeT0iMTYzIi8+PGNpcmNsZSByPSIxIiB0cmFuc2Zvcm09InJvdGF0ZSgtMTIyLjUgMTU4IDc1LjQpc2NhbGUoMzUuNTQ1NDYgOTcuNjIwNDgpIi8+PGNpcmNsZSByPSIxIiB0cmFuc2Zvcm09InJvdGF0ZSgzMiAtNDI4LjcgMTg0LjYpc2NhbGUoNTIuNTYxNDEgMzAuODAyOTgpIi8+PGNpcmNsZSByPSIxIiBmaWxsPSIjZmRlNzRlIiB0cmFuc2Zvcm09Im1hdHJpeCgxODQuMjkzMSAuNDg3NyAtLjA3OTE0IDI5LjkwNDggMTE1LjEgMTUwLjcpIi8+PC9nPjwvZz48L3N2Zz4=)![Easiest Admin - Summer 2024](https://memberpress.com/wp-content/themes/memberpress-theme/images/verification-badges/easiest-admin.png)

![Easiest Setup - Summer 2024](data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyOTkiIGhlaWdodD0iMzg5Ij48ZyBmaWx0ZXI9ImJsdXIoMTJweCkiPjxyZWN0IHdpZHRoPSIyMDAlIiBoZWlnaHQ9IjIwMCUiIHg9Ii01MCUiIHk9Ii01MCUiIGZpbGw9IiM4MzgzODMiLz48cmVjdCB3aWR0aD0iMTAwJSIgaGVpZ2h0PSIxMDAlIiBmaWxsPSIjODM4MzgzIi8+PGcgZmlsbC1vcGFjaXR5PSIuNSIgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoLjggLjgpc2NhbGUoMS41MTk1MykiPjxlbGxpcHNlIGN4PSI5NCIgY3k9IjM0IiBmaWxsPSIjZmZmIiByeD0iMTQyIiByeT0iMjAzIi8+PGNpcmNsZSByPSIxIiB0cmFuc2Zvcm09InJvdGF0ZSgtMjggNTU2LjIgLTI3OC45KXNjYWxlKDkwLjAxMzk0IDI0Ljg4NTU3KSIvPjxjaXJjbGUgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoLTYuOTcyNTcgMjkuMzE4ODggLTQ3LjY0MjQ2IC0xMS4zMzAyNSAxOSAyNDguOCkiLz48ZWxsaXBzZSBjeD0iMTIwIiBjeT0iMTQzIiBmaWxsPSIjNWRjNWZmIiByeD0iMTk2IiByeT0iMjQiLz48L2c+PC9nPjwvc3ZnPg==)![Easiest Setup - Summer 2024](https://memberpress.com/wp-content/themes/memberpress-theme/images/verification-badges/easiest-setup.png)

![High Performer - Summer 2024](data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyOTkiIGhlaWdodD0iMzg5Ij48ZyBmaWx0ZXI9ImJsdXIoMTJweCkiPjxyZWN0IHdpZHRoPSIyMDAlIiBoZWlnaHQ9IjIwMCUiIHg9Ii01MCUiIHk9Ii01MCUiIGZpbGw9IiM3NDc0NzQiLz48cmVjdCB3aWR0aD0iMTAwJSIgaGVpZ2h0PSIxMDAlIiBmaWxsPSIjNzQ3NDc0Ii8+PGcgZmlsbC1vcGFjaXR5PSIuNSIgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoLjggLjgpc2NhbGUoMS41MTk1MykiPjxlbGxpcHNlIGN4PSI5OCIgY3k9IjgyIiBmaWxsPSIjZmZmIiByeD0iMTIyIiByeT0iMTU3Ii8+PHBhdGggZD0ibTIzMC43IDIzOC4yLTc1LjUgNDcuMi0yNi00MS42IDc1LjYtNDcuMnoiLz48Y2lyY2xlIHI9IjEiIGZpbGw9IiNmZmYiIHRyYW5zZm9ybT0ibWF0cml4KDYxLjI1ODEgOC4xNzM1OCAtOC42NDg3NiA2NC44MTk0NyAxNy4xIDU0LjEpIi8+PGNpcmNsZSByPSIxIiB0cmFuc2Zvcm09Im1hdHJpeCg5OC40ODI2OCA2NS45NzcwMyAtMjAuMTIyNzIgMzAuMDM2ODEgMTUuNSAyNTUpIi8+PC9nPjwvZz48L3N2Zz4=)![High Performer - Summer 2024](https://memberpress.com/wp-content/themes/memberpress-theme/images/verification-badges/high-performer.png)

![Momentum Leader - Summer 2024](data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyOTkiIGhlaWdodD0iMzg5Ij48ZyBmaWx0ZXI9ImJsdXIoMTJweCkiPjxyZWN0IHdpZHRoPSIyMDAlIiBoZWlnaHQ9IjIwMCUiIHg9Ii01MCUiIHk9Ii01MCUiIGZpbGw9IiM3NDc0NzQiLz48cmVjdCB3aWR0aD0iMTAwJSIgaGVpZ2h0PSIxMDAlIiBmaWxsPSIjNzQ3NDc0Ii8+PGcgZmlsbC1vcGFjaXR5PSIuNSIgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoLjggLjgpc2NhbGUoMS41MTk1MykiPjxlbGxpcHNlIGN4PSI5MyIgY3k9IjgxIiBmaWxsPSIjZmZmIiByeD0iMTMyIiByeT0iMTU2Ii8+PGNpcmNsZSByPSIxIiB0cmFuc2Zvcm09Im1hdHJpeCgtNjIuMDU3MjMgNDAuMjcxNjkgLTEzLjgzMDI1IC0yMS4zMTE5MyAxNzkuOCAyMzkuOCkiLz48Y2lyY2xlIHI9IjEiIHRyYW5zZm9ybT0ibWF0cml4KC0xNC40NTcwNCAtMzEuMTQ1MDIgNDYuMDc4MTkgLTIxLjM4ODc4IDEzLjQgMjU1KSIvPjxjaXJjbGUgY3g9Ijc0IiByPSIyMTQiIGZpbGw9IiNmZmQyYzkiLz48L2c+PC9nPjwvc3ZnPg==)![Momentum Leader - Summer 2024](https://memberpress.com/wp-content/themes/memberpress-theme/images/verification-badges/momentum-leader.png)

## Footer

 

#### Company

#### Features

#### Integrations

#### Case Studies

#### Helpful Links

 

![MemberPress logo](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7)![MemberPress logo](https://memberpress.com/wp-content/themes/memberpress-theme/images/memberpress-logo-white.svg)

[](https://twitter.com/memberpress)
[](https://facebook.com/memberpress)
[](https://www.instagram.com/memberpress)
[](https://www.youtube.com/c/MemberPressPlugin)

						Copyright © 2025 Caseproof, LLC. All rights reserved.
					

[Privacy Policy](https://memberpress.com/privacy/)
/
[Refunds](https://memberpress.com/terms/#refunds)
/
[Terms & Conditions](https://memberpress.com/terms/)
/
[FTC Disclosure](https://memberpress.com/privacy/)
/
[MemberPress Coupon Code](https://memberpress.com/memberpress-coupon-code/)

 

Username or E-mail

Password

 Remember Me

 

 

[Forgot Password](https://memberpress.com/sign-in/?action=forgot_password)

			×			

 

 

  ![](https://px.ads.linkedin.com/collect/?pid=3219420&fmt=gif)


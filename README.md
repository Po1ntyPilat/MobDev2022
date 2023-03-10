# "The DoToo" - MobDev2022 FinalProject 
#### Authors: Eduard Žurin, Maksimilian Tsenkman, Aleksander Zahharov

## The main idea
We thought that adding a calendar API into your ToDo list will increase a likelyhood of a user completing those goals.

Our app urges you to be proactive and helps you to reach your goals more sequentially.

When creating tasks user can add title, steps and set an alarm time (in case he forgets to do the task). 

The app includes an option to make a contribution to the progress of the mankind and donate a choosen sum to the developers via Google Pay in only two clicks.

## How to run
There are two project that we wanted to merge together (The ToDo and Google Pay Api), but we did not succeed.
Googe pay API project ("kotlin.zip") can be viewed separately.

The ToDo list project is compiled and built as any other project.

In order to test GPay project you need to enter your Google account on emulator (or you physical devise) in "Settings" -> "Passwords & Accounts".
And you should have at least one real card attached to your account. The GPay app is in the test mode, so no real money will be withdrawn.

## Difficulties analysis
We have encountered many difficulies along the way.
Most significant were Graddle compatibility. This is the reason we were not able to merge projects together.

Aditionally, connecting checkboxes to the delete button. We used fragments, therefore we had to take every view within the recyclerView into account.
There were also difficulties making an app open with a click on a notification (in future we want to finaly add this option).

Implementing the GPay API was also a chellenge because Google's video gides and trial repository contains slightly different information than it is written in the oficial documentation. Some things now seem obvious, but it is hard for a newcomer to understand.

The initial idea was to create a WiFi Heatmap and Eduard spent a lot of time trying to implement it, but realised that this is too complicated.

## OWASP
#### "MSTG-STORAGE-2. No sensitive data should be stored outside of the app container or system credential storage facilities."
PASSED.
Data is stored localy using RoomDB.

#### "MSTG-STORAGE-3. No sensitive data is written to application logs."
NOT PASSED.
Some of our logs contain sensitive informaton as it was used for testing the app during the development.
We should delete them.

#### "MSTG-PLATFORM-1. The app only requests the minimum set of permissions necessary"
PASSED.
We only ask for notification permission.

#### "MSTG-PLATFORM-3. The app does not export sensitive functionality via custom URL schemes, unless these mechanisms are properly protected."
PASSED.
We do not use URLs.

## Who did what
Eduard Žurin: Room DB implementation.

Maksimilian Tsenkman: The todo list implementation, design.

Aleksander Zahharov: Google Pay implimentation, documentation

## Resourses
Oficial Google Pay try-yourself app repo: https://github.com/google-pay/android-quickstart/tree/475b218072b4568bcc07db478f3084fe1e84ad49

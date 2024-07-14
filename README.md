# `July 2024` r/Code (NOT HAPPENING) - ~~<kbd>Friday, July 15th (Midnight EDT)</kbd> - <kbd>Friday, July 22 (Midnight EDT)</kbd>~~

r/Code is a collaborative coding project where users can contribute code and eventually construct a complete program. All users are welcome to participate, but any form of botting and/or automation designed to manipulate the codebase such that other users are unable to commit their code is strictly prohibited. The July r/Code event will run from Friday, July 15th (Midnight EDT) to Friday, July 22 (Midnight EDT). The rules for this event are as follows:

# Rules
* The primary method which users can use to contribute to r/Code is through Pull Requests. Users can use PRs to make edits to `main.py` and `input.txt`.
* A PR can be created every 5 minutes, and any PR created within 5 minutes of another previously-created PR will be discarded.
* Each user is allowed to contribute up to 500 character additions and up to 500 character deletions (as calculated by `git diff`) per PR. This limit applies collectively to all modified files.
* PRs will be automatically merged if the resultant program does not result in any errors from pylint and can be executed without any errors.
* If necessary, an Issue can be created to bring attention to important concerns regarding the management of r/Code. Discussions are also enabled on this repository to facilitate inter-player communication.
* Any malicious code submitted into r/Code with the malicious intent of causing harm upon any computer system or causing undue load on a computer system will be purged immediately and the user banned from participating in r/Code.
* The r/Code moderators reserve the right to restrict access to or amend data in r/Code at their discretion. All code must be licensed under the MIT license.

# Technical Notes
* Programs are tested using Python 3.10 and default dependencies, and must not exceed an execution time of 2 minutes.
* Programs can accept input, but such data must be provided in a separate input file, which is then piped into the program during execution. A common source of a program timing out is when the program tries to read more data from STDIN than input.txt has to provide.
* The 5 minute timeout also applies to rejected PRs to prevent abuse. We highly encourage users to test their programs locally before submitting a PR.
* No line of code should be more than 127 characters and have a complexity score higher than 10 to promote code readability. The commands used to enforce this rule are attached below.

# Implementation Details
The commands used to validate submissions are as follows:
```
# Ensure python3.10
pip install flake8
flake8 . --count --select=E9,F63,F7,F82 --max-complexity=10 --max-line-length=127 --show-source --statistics
echo input.txt | python main.py # A time limit of 2 minutes is imposed on all submissions
```

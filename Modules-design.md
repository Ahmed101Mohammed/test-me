# Modules Design

## data_base_needed_functionality Module:

### Module responsipilities:
- The only module have the ability to use data-base-easy-use module
- This module create the main db structure.
- This Module should contain main functionality of the app accourding the data-base structure.

### Module Functions:
- Constructore: When the Main class of the module create, it should create automatically the main structure of the data base.

- get_user_password: This function take a user name and return user password, or false, if the user doesn't exist.

- delete_user_data: This function take a user name and delete every thing relate to him in the data-base.

- get_user_email: This function take a user name and return user's email, else return false.

- update_user_password: This function take a user_name and new_password, it sure that the password is valid by "is_valid_password" method from Register_Sign Module, 
  then replace the ancient password with the new, and return true if it's done else false.

- add_scope: it take a data of scope and create a new scope in db.

- show_scopes: it return first 10 scopes if it doesn't get a number, if it get a number it return 10 scopes form the number taken.

- get_question: This function take number of string, it take number, find the question who had the id that equal the number, if it take string find the question with 
  date that equal the taken string, It may take a list with numbers or strings, or compination of both.

- get_all_questions: it return first 10 of questions in db it there is no input, if it get number input return 10 of questions from the number added.

- add_question: it take a data of question and save it in db.

- remove_question: it remove a question by its id.

- remove_scope: it take a scope id and remove it, and any question related to the scope.
------------------------------------------------------------------------------------------------------------------------------------------------------
## Register_Sign Module:
### Module responsipilities:
- Give the ability of creating new accounts.
- Give the ability to sign an acount.
- Give the ability to return the account if you forget it.
### Module Functions:
- register: This function ask user to input three parts of data:
    1. user_name: This should be unique and without spaces or chars not included in this list: ["_"], the length of User name should be > 5 chars
    2. password: This have the same rules of chars for user_name except that should be large than 7 chars and password isn't unique.
    3. email: it should be valid and shour that this email is the own of the user.
    this function check that every input is valid and save this data in the DB, the function print a message if the saving is done or if existing of an error.
        
- sign_in: This function ask user to input two parts of data:
    1. user_name: check that the user name is valid, and exist.
    2. password: check that the password is valid.
    the function will search about the user_name in DB, and return the password of the user_name, it return a message if the user_name is not exist, else the function 
    will compare between the passward from DB, and the passward that user input.

- get_account_back: This function ask user to check it's email, and right the number that he get, if true, he/she can access his account else return error number and 
    send a new number for him/her, if use do wrong three times, delete user account.

- delete_account: This function take a user_name then delete every thing relete to the user_name. 
        
- is_valid_normal_input: This function check the input that has just numbers and chars and "_" only, the function return true, or false.
        
- length_more_than: This function take two inputs:
    - input which client want to chech that length of it is more the second input.
    - is a number.
    the function will return true if the first inpus is longer than the number in the second else false.
        
- is_valid_user_name: check the user_name that input to the function, valid and it's length more than 5 chars.

- is_valid_password: This function take a password and return true if it's valid normal input and has length more than 7 chars.
    
- is_unique_user_name: take a user_name then return true if user name uniqu else false.

- is_valid_email: check that the input is a valid email by emails rules:
    - it must not be one email for two accounts.
    - each email should contain "@Something.something" .
    - emails doesn't contain spaces.
    - emails may contain in the end of it a series of ".somethinng.something.something.and_so_one"
    - emails shouldn't end wiht ".com" word.
    - explore for more rules for emails.
   
- check_email: This function take and valid email and send a random number, and return a wrong message if the sending is field, else ask the client to check his/her 
    email and input the number. the funciton return true if the number input is the same of the sending number, else false.

- is_username_appropriate_for_register: Check that the user name is valid and unique.

- is_username_appropriate_for_sign: Check that the user name is valid and not unique.

- is_password_appropriate: Check that the password is valid and equal the password of user_name input.

- is_email_appropriate: Check that the email is valid and the number message that send is equal the user input.

---

## Settings Module:

### Module responsipilities:
- Give the ability to user to know or change main authantication data.
- For now user can't change any data ecsept password.

### Module Functions:
- update_password: This function take a new password and check user email, by using "check_email" method from Register_Sign Module, if checked email return true and 
    then new password is valid  accept the changes and change the password in data-base then return true else false.

- my_info: This function return the user name and user email, this like a data not a presentation in string.

---

## Scope Module:

### Module responsipilities:
- This medule is the main catogerised tool or way for the questions, to seperate deferent questions from each others.
- It give the ability to exploring the ancient questions added before.
- It give the ability to add, remove or edit any question.

### Module properities:
- name: it contain the name of the scope.
- quesiotns: it contain the questions that the user used.

### Module Functions:
- show_question: This function take Id or "*" or several Ids or date of several dates or compaining of all of this and return the quesions and save them in the 
    "questions"

- show_quesiton_by_id: This function take Id or Id(s) and return list of quesitons.

- show_quesiton_by_date: This function take date or date(s) and return list of quesitons

- show_all_questions: This function return all of the quesitons.

- delete_question: This function take Id of an question and delete it.

- add_question: This function ask for data of question like: [question_text, question_taq, question_right_answer, *Question_others_not_right_answer if the question     
    is't written question*], and save the question and return true if it done else false.

- edit_question: it take the Id of question and treate with the edit_queistion method from "Question" Module.

- remove_scope: it remove the hole scope.

- edit_scope_name: it edit the scope name. 

---
## Question Module:

### Module responsipilities:
- This module can edit many of question proberities.
- This module rate many details of how user treate with the question.
- This module change the answers order, and rate the user answer.

### Module properities:
- text: It contain the text of the question.
- right_answer: It contain the tight answer text, it a text if the type of question is 'O' or 'W', and a list of the quesion type is 'M'.
- type: it contain char of three : O => one-choice question, M => multi-choices question, W => writen question.
- date: It contain the first history of the question, when it added.
- tag: It shouldn't but it's better to added, and it make questions in one domain contained in one category under the domain.
- appearance: It contain a number of the times question appear for the user to answer.
- user_right_answers: It contain the number of the question answered right from the user.
- other_choices: It's essencial for question that had type one-choice question and multi-choices question, and it contain list of other answers.
- priority_of_appearance: it's contain a number that explain the periority of the question to appear to the user, and it calculate by this: (user_right_naswers * 
    appearance)
- why: is a text explain why the write answer is right.

### Module Functions:
- update: it ask the user to choose the properity he want to update, and it should be answer by of of these chars:
    - **t**: it represent that the user want to change the text of the question.
    - **ra**: it represent that the user want to change the right_answer properity.
    - **tag**: it represent that the user want to change the tag of the question.
    - **oc**: it represent that the user want to change the other choices if his question from one-choice question or multi-chioces question.
    - **why**: it represent that the user want to change the explain of the right answer.

- update_text: it take a text and replace it with question old text and save the update in the db.

- update_right_naswer: it take a text of the right answer and replace it with the old one, and save the update in the db.

- update_tag: it take a text and replace it with the tag, and if there no text it remove the tag and make its value NONE, and save the update with empty text in db.

- update_other_choices: it take many choices and replace them with the old choices and save the update in the db.

- update_why: it take text and replace it with the old explain of the quesion, and save the update in the db.

- get_ready: it create a list of the right answer and other answers and orderd them with random way, it dependent on question type.

- is_write: it compair betwen write answer and user input for the answer and detect if that the user answered write or no, and the compireson depend on question type
    it return true of false.

- increase_user_right_naswers: it increase the number of user right answers properity.

---
## Test Module:

### Module responsipilities:

### Module properities:

### Module Functions:

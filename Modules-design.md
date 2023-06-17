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
          this function check that every input is valid and save this data in the DB, the function print a message if the saving is done or if existing of an
          error.
        
        - sign_in: This function ask user to input two parts of data:
            1. user_name: check that the user name is valid, and exist.
            2. password: check that the password is valid.
          the function will search about the user_name in DB, and return the password of the user_name, it return a message if the user_name is not exist, else
          the function will compare between the passward from DB, and the passward that user input.

        - get_account_back: This function ask user to check it's email, and right the number that he get, if true, he/she can access his account else return 
          error number and send a new number for him/her, if use do wrong three times, delete user account.

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
    
        - check_email: This function take and valid email and send a random number, and return a wrong message if the sending is field, else ask the client to
            check his/her email and input the number. the funciton return true if the number input is the same of the sending number, else false.

        - is_username_appropriate_for_register: Check that the user name is valid and unique.

        - is_username_appropriate_for_sign: Check that the user name is valid and not unique.

        - is_password_appropriate: Check that the password is valid and equal the password of user_name input.

        - is_email_appropriate: Check that the email is valid and the number message that send is equal the user input.
------------------------------------------------------------------------------------------------------------------------------------------------------
## Settings Module:
### Module responsipilities:
        - Give the ability to user to know or change main authantication data.
        - For now user can't change any data ecsept password.
### Module Functions:
        - update_password: This function take a new password and check user email, by using "check_email" method from Register_Sign Module, if checked email return     
          true and then new password is valid  accept the changes and change the password in data-base then return true else false.
        - my_info: This function return the user name and user email, this like a data not a presentation in string.
------------------------------------------------------------------------------------------------------------------------------------------------------
## Scope Module:
### Module responsipilities:
        - This medule is the main catogerised tool or way for the questions, to seperate deferent questions from each others.
        - It give the ability to exploring the ancient questions added before.
        - It give the ability to add, remove or edit any question.
### Module properities:
        - name: it contain the name of the scope.
        - quesiotns: it contain the questions that the user used.
### Module Functions:
        - show_question: This function take Id or "*" or several Ids or date of several dates or compaining of all of this and return the quesions and save them in
          the "questions"  
        - show_quesiton_by_id: This function take Id or Id(s) and return list of quesitons.
        - show_quesiton_by_date: This function take date or date(s) and return list of quesitons
        - show_all_questions: This function return all of the quesitons.
        - delete_question: This function take Id of an question and delete it.
        - add_question: This function ask for data of question like: [question_text, question_taq, question_right_answer, *Question_others_not_right_answer if the 
          question is't written question*], and save the question and return true if it done else false.
        - edit_question: it take the Id of question and trate with the edit_queistion method from "Question" Module.
        - remove_scope: it remove the hole scope.
        - edit_scope_name: it edit the scope name. 
    

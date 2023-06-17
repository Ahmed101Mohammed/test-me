# V: 1.0.0
## Bussiness part

### What problem I try to solve?
- When I study I hate to rev my lessons with reading, I don't can check if I do good or not, so I find that 
    If I have ability to summurise my lessons in some questions, and for rev I just can solve some of my
    questions it can make me fell that I do good, and may make my study is more funny and good.
    I think also that I need in each time when I rev lesson to rev just top questions that I answer false in last
    time, it can cover my weakness, and improve me in my bad point.
- When I read a book I want to remember it's ideas with out reread it every year (for example), so I find that
    If i summuries my book to many questions cover the important aspects, it can help me to rev with answering
    some question instead of reading the whole book.
- When I study knowladgable course, and it debend in many information rather than many applied of the information
    I know that I will forget this lessons, and I will be lazy to review the course, so I find that will be great
    if I summuries the whole course in many questions, and I can test my self when I need to rev the course.

### What new we will learn?
- Learning from software architict roadmap.

### Overview of the project:
- The project is a test personal knowladge, that provide the ability of create questions under 
    specific title or scope, then the user can ask the program to ask him several quistions, and give him
    a grade in the end of an exam.

### Details of the project:
- Registering: give the ability to user to register (make a new account), and it will be sample, Just:
        - User name
        - User passward
        - User email (to send new passward for the user to access againg to his account, and he can change his passward)

- Sign in: give the user the ability to sign to his account, the information can he sign with is:
        - User name
        - passward

- The project servieces:
    - Create new scope (The scope is the big title user put question under it): give the user tha ability to
      create new scope and questions to the scope.
    - Add questions for currunt scope: give the user the ability to create new questions under the general scope.
    - Test me: give the ability to user to choose the kind of test he want.

- Questions:
    - Questions types: The user have the ability to test him self in defferent types of questions:
        1. one choice question (question with many choices and there is one good choice)
        2. Multi choices question (Question with many choices adn there are many write choice)
        3. Write question (Question have write answer and the user chouse the parcentage of similarity, that 
            make the answer is right answer.)
    - Properites of questions:
        - Type: it's the type of question: Multi, one_choice, Wtiten.
        - Tag: each question has a tag, and the tag relate to the scope, and it make it easy to 
            choose questions under specific tag.
        - Perfictionism: this proberity give a precentage for how goodly the user answer the question and it
            counted by this = (number of the question appearance / number of right answer) * 100
        - appearance: the number of the question appear in exams for the user.
        - user_right_answers: the number of onces that user give a right answer for the question.
        - right_answer: it's just text for on choice or write questions, and list for multi choose questions.
        - other_choices: is a list of choises appear to the user in choose questions to choose from, it's NONE 
                            for writen questions.
        - why: is a text apear when the user, answer the question to explain why the right answer, is write.
        - FUN update: it give the ability to edit a question and update it.
        - FUN remove: it give the ability to remove a question.
        - FUN ready: it make a list of the wright answer, and other choices, and ordered them in random way
                        to apear it for the use, it only for choices questions.
        - FUN is_right: it make a compirison between user answer and the right answer.
- Test:
    - Test settings: The user have the ability to test him self in defferant ways can determin with the test 
        settings.
            1. scope of testing: in this setting the use should determain what is the scope or multi scopes he
                want to test him self in.
            2. tags of testing or all: in this setting it by defulte "all", and it main that the user want to test
                him self in the whole of the scopes he choese, and he can use tag or multi tags from the scope he
                choose or multi scopes.
            3. Number of questions: the use can choose the number of questions in the exam.
            4. Timer: the user can choose if he want a timer for answering each question, or not(not timer)
            5. number of minuts: if the user choose true for the timer, then field of minuts appear, and 
                give him the ability to choose number of minuts for each exam, it chould accept float numbers 
                like: (0.1).

    - Test Machanism: The test have questions that divid in two parts:
        First: half of questions from the lowest perfictionism questions.
        Seconed: half of questions from the lowest appearance questions.
        More details: 
        - The questions are generated randomly for the user, and in the end of the test the user can
        have a grade of the test, and he can retest the same test, unlimited times.
        - The test appear in a new window, with one question appear in the time, and with next buttom you can
            access to the next question, and you can get back. the next question can generate auto when the time
            is out.
        - When the user choose the right answer a grean color will be in his answer, with slide apear to tell 
            him why this is right, and when the user answer rong answer, red flag in his answer and grean in the
            wright answer, with a same slide of explanation for the right answer.
        - If the question is writen question and the answer is more than 70% right answer it make the naswer
            right, else it make it false, (apear to the user the percante of his answer.)

__________________________________________________________________________
## Programming part
    
### Project tools:
    - Python
    - SQL lite

### Project Modules:
    - data-base-easy-use module (It's a module to facilate the sql lite commends).
    - data-base-needed-functionality module (It's a module to prapere main functions that use the data-base-easy-use module and build the main structure of db).
    - Register/Sign. (For all registering ans signing data or functinality).
    - Settings. (for changing passward functionality, and ather future settings properities)
    - Scope (For all scoping and tags data and functionalities).
    - Question (For all Question data and functionalities).
    - Test (For all tests data and functionalities).

### Check steps for architect Modules. 
    - Descripe each of the module.
    - Determine each of the module functionalities and proberites.
    - Descripe the functions of each module.
    - build a senarios for deferent setuation, and how the modules used each others.
    - Build the modules in the datagrams, and determin the relation between them.

### Check steps for building the app.
    (NOTE: Any update you relize in this step you should start it from the "Check steps for architect Modules" step.)
    - look at the Description of each modules.
    - built the functions and proberites of the module: -> Check steps for building a function:
        - Analyse the description of the function and determine the functionality of the function.
        - Build the test cases of the function.
        - Code the function.
        - Make the test and debug. (NOTE: the tests should runing each time you add a new function or functionality of modufy it, and you don't need to test ready 
          modules).
    - Each module has own test file.
    - use the senarios of deferent setuations in the step 4 of "Check steps for architect modules" to build the main app.

### Data-base design: it contain 4 tables:
    - users: this table will contain user data in 4 columons:
        1. usser_id.
        2. user_name.
        3. password.
        4. email.

    - scopes: it contain 3 culomuns:
        1. scope_id.
        2. scope_name.
        3. user_id.

    - tags: it contain 3 culomuns:
        1. tag id.
        2. tag name.
        3. scope_id.

    - questions: it contain 5 culomuns:
        1. question_id.
        2. question_text.
        3. right_answer_text.
        4. scope_id.
        5. tag_id.
    
    - answers: it contain 3 culomuns:
        1. answer_id.
        2. answer_text.
        3. question_id.

    

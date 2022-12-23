#My Views
I read the code and get out know some points.
1) Code is developed using repository design pattern.
2) From class names it looks that it is developed for `booking` system but from function names it seems about `job management`

##Good about Code
1) It is good that repository is used for development. 
2) It increases reusability and different type of logics on different places.
3) Business Logics are written in repository class.
4) It is good that common functions are written BaseRepository.
5) Code is cleaned controllers.

##Bad about code
1) BookingRepository class name should be JobRepository. Because Job model related business logics are implemented inside.
2) Many functions could be extract in different classes from BookingRepository. eg `userLoginFailed()`, `sendNotification()`
3) Don't understand why `logger->pushHandler` added in repository constructor.
4) `find()` method is defined in `BaseRepository` then why are not using to find the model. Often this code is written in `BookingRepository` `Job::find()` it should be `$this->model->find()`
5) Many other `BaseRepository` methods  also not used.
6) If some details are fetching related users then it should be `UserRepository`
7) `QueryBuilder` queries are often used in code. It should be with `Eloquent` 
8) No comments added in code. Very difficult to understand the code.
9) Nested loops and if-else are used often
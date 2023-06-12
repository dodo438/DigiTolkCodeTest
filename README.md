

## My thoughts towards code standards

It is an ok code due to following reasons:

- Changing of namespace was supported in Laravel 5.0. You should not change the namespace, as, many commands like `make:model` or `make:controller` uses default namespace.
- There should be more controllers if you need more than one functionality. `BookingController` should have just CRUD operations and for the rest group of functionality should be in separate controller.
- `BookingRepository` is the worst code as it contains more than 2000 lines, it should be broken into multiple files.
- `BookingRepository` has many functions that are not dependant on a `Booking` repository, so, they should be in separate files/helpers or other related repositories  (e.g. `convertToHoursMins` method should be in helper file).
- `BookingRepository` constructor is not backward compatible.
- Making of Repository Class is a very good approach for making your code scalable.
- It would be better if we had an Interface for `BaseRepository`.
- Instead of using `$mailer` as a parameter to constructor, it should be initialized in constructed.
- Calling the relation or nested relation should contain specific columns that are required. For example `user.userMeta:user_id,id,name`


#### There are still lots of refactoring can be done.

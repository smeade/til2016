# RSpec "Only Failures"

Configure rspec for "Only Failures" support

“The --only-failures option filters what examples are run so that only
those that failed the last time they ran are executed. To use this
option, you first have to configure config.example_status_persistence_file_path, 
which RSpec will use to store the status of each example the last time it ran.

Once configured, you can run only failing specs with:

`rspec --only-failures`

There's also a --next-failure option, which is shorthand for
--only-failures --fail-fast --order defined. It allows you to
repeatedly focus on just one of the currently failing examples, then
move on to the next failure, etc.”

See:
https://relishapp.com/rspec/rspec-core/docs/command-line/only-failures

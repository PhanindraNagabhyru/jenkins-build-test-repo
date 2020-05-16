Failing test command



mvn -Dtest=FailingApplicationTests test

Passing test command

mvn -Dtest=WorkingApplicationTests test


Steps

1) Trigger pipeline on push to git repo
2) git clone repo
3) Run passing test
4)     zip git repo.   create new PassingDir with timestamp and copy
5) Second pipeline branch
6) Run failing test
7)     Output error message

# Leap Year

## Task:
Write a program which will tell you whether or not a given year is a leap year.

#### Rules:

A leap year occurs:

- On every year that is evenly divisible by 4...
  - except every year that is evenly divisible by 100...
    - unless the year is also evenly divisible by 400.

Or:

To determine whether a year is a leap year, follow these steps:

1. If the year is evenly divisible by 4, go to step 2. Else, go to step 5.
2. If the year is evenly divisible by 100, go to step 3. Else, go to step 4.
3. If the year is evenly divisible by 400, go to step 4. Else, go to step 5.
4. The year is a leap year (it has 366 days).
5. The year is not a leap year (it has 365 days).
```
$ ./leap 1997
nope, 1997 is not a leap year

$ ./leap 1996
yes! 1996 is a leap year!

$ ./leap 1990
nope, 1990 is not a leap year

$ ./leap 2000
yes! 2000 is a leap year!
```

To complete this task you will need to know about [modular arithmetic](https://betterexplained.com/articles/fun-with-modular-arithmetic/)
and [logical operators](https://javascript.info/logical-operators).

#### Don't forget about git
Remember to initialise a repository in your terminal and online (do not choose to `initialise with a readme`)
```
cd ~
mkdir -p workspace/leap-year
cd workspace/leap-year
git init
git remote add origin <link-to-where-your-repo-is-online>
```

After you are ready to make your first commit:
```
git status
git add <files-you-have-made>
git commit -m "first commit - <what does it do so far?>"
git push -u origin master
```

Remember, you only need to `git push -u origin master` the first time, after that
`git push` is enough.
Commit regularly in small incremental steps. Don't just wait until the end; you
want to save your work as it progresses.

### Challenge Yourself!
- Set a default for when no year is passed to your script.
- Write a loop to run your leap-year calculator against every year in the last century.
  - make sure you print out which years are and aren't.
- can you [TDD](https://github.com/fouralarmfire/square-one/blob/master/tutorials/fizzbuzz-tdd.md#intro-to-test-driven-development-fizzbuzz) this program?

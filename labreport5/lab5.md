# Debugging Scenario

1. Post
Hello,

My bash grading script works on all the test Github repositories except one, and ends up throwing the error `grade.sh: line 44: tests): syntax error in expression (error token is ")")`.
Here are test Github repositories that it passes on:
![Passed test](lab5_img1.png)
Here is the test Github repository that it throws an error on, and the symptom:
![Failed Test](lab5_img2.png)
Here is my grade.sh script for reference:
![Failed Test](lab5_img3.png)

Since the symptom references line 44, I would guess that the bug may be that I am using improper parentheses syntax in this line 44 in `grade.sh`: `successes=$(( test - failures ))`. However, the syntax seems correct to me and I am confused why an error is only being thrown for one test and not the others.

3. TA Response
  Hey Katelyn,
I recommend using `echo test` and `echo failures` to see what your variable values are. It may not neccessarily be a syntax error. The `awk` command may not be splicing correctly, so maybe check if your variables are saving the correct numbers.

5. Student Response
Thank you, I fixed the error!

```
cat junit-output.txt
lastline=$(cat junit-output.txt | tail -n 2 | head -n 1)
if [[ $(echo $lastline | awk '{print $1}') == "Tests" ]]
then
    test=$(echo $lastline | awk -F', ' '{print $1}' | awk '{print $3}')
    failures=$(echo $lastline | awk -F', ' '{print $2}' | awk '{print $2}')
    successes=$(( test - failures ))
else
    successes=3
    test=3
fi
echo "Your score is $successes / $test tests passed"
```
5. Information about Setup


# Reflection

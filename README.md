### Understanding how it works.

![Async1.png](ReadMeImgs/Async1.png)

Explanation:

"println!("Ferdinand's Computer: Test 2: Electric boogaloo!");" happens synchronusly

spawner.spawn is creating an asynchronus recipe that will be run by executor later

"println!("Ferdinand's Computer: This is a test!");" happens synchronusly

drop(spawner). Tell the executor that there's no more spawner related to it beyond this point.

"println!("Ferdinand's Computer: Test 333333!");" happens synchronusly

executor.run() is running all the async task that is related to it. It only run code within the async spawner itself, the reason it doesn't re run "Ferdinand's Computer: This is a test!" is because it's outside the async code

when the executor is done running all it's related async task, the next "println!("Ferdinand's Computer: 4444444!");" is executed

---
# Lab Report 3: Bugs and Commands
---

# Part 1: Bugs

> Function in question

```  
// should change the input array to be in reversed order
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
        arr[i] = arr[arr.length - i - 1];
    }
}
```

> Failure-inducing input

```
@Test 
public void testReverseInPlace() {
    int[] input1 = {1, 2, 3, 4, 5};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{5, 4, 3, 2, 1}, input1);
}
```

> Non failure-inducing input

```
@Test 
public void testReverseInPlace() {
    int[] input1 = { 3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3 }, input1);
}
```

> Symptom

![Image](failedjunittest.png)

![Image](successfuljunittest.png)


> Bug

```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
        arr[i] = arr[arr.length - i - 1];
    }
}
```

```
static void reverseInPlace(int[] arr) {
    int p;
    for(int i = 0; i < arr.length/2; i += 1) {
        p = arr[i];
        arr[i] = arr[arr.length - i - 1];
        arr[arr.length - i - 1] = p;
    }
}
```

The approach in the original function was incorrect as it couldn't replace the values of the second half of the array with the ones from the first half.
We require a placeholder variable to hold the value of the elements in the first half in order to swap the values of both halves of the array.
The second correct function only loops through half of the array and uses the placeholder variable to swap all the values resulting in a working function which reverses an array.


---

# Part 2: Researching commands

`less` is a command which allows backward movement in the file as well as forward movement.  Also, less does not have to
read the entire input file before starting, so with large input files it starts up faster than other text editors.

> 4 interesting options with less 

1) Option 1

`-E` 

**Example 1:**

*Command:*

```
less -E 911report/chapter-1.txt
```

*Output:*

```
WE HAVE SOME PLANES

    Tuesday, September 11, 2001, dawned temperate and nearly cloudless in the eastern United States. Millions of men and women readied themselves for work. Some made their way to the Twin Towers, the signature structures of the World Trade Center complex in New York City. Others went to Arlington, Virginia, to the Pentagon. Across the Potomac River, the United States Congress was back in session. At the other end of Pennsylvania Avenue, people began to line up for a White House tour. In Sarasota, Florida, President George W. Bush went for an early morning run.

    For those heading to an airport, weather conditions could not have been better for a safe and pleasant journey. Among the travelers were Mohamed Atta and Abdul Aziz al Omari, who arrived at the airport in Portland, Maine.

INSIDE THE FOUR FLIGHTS

Boarding the Flights

    Boston: American 11 and United 175. Atta and Omari boarded a 6:00 A.M. flight from Portland to Boston's Logan International Airport.

    When he checked in for his flight to Boston, Atta was selected by a computerized prescreening system known as CAPPS (Computer Assisted Passenger Prescreening System), created to identify passengers who should be subject to special security measures. Under security rules in place at the time, the only consequence of Atta's selection by CAPPS was that his checked bags were held off the plane until it was confirmed that he had boarded the aircraft. This did not hinder Atta's plans.

    Atta and Omari arrived in Boston at 6:45. Seven minutes later, Atta apparently took a call from Marwan al Shehhi, a longtime colleague who was at another terminal at Logan Airport. They spoke for three minutes.

    It would be their final conversation.

    Between 6:45 and 7:40, Atta and Omari, along with Satam al Suqami, Wail al Shehri, and Waleed al Shehri, checked in and boarded American Airlines Flight 11, bound for Los Angeles. The flight was scheduled to depart at 7:45.

    In another Logan terminal, Shehhi, joined by Fayez Banihammad, Mohand al Shehri, Ahmed al Ghamdi, and Hamza al Ghamdi, checked in for United Airlines Flight 175, also bound for Los Angeles. A couple of Shehhi's colleagues were obviously unused to travel; according to the United ticket agent, they had trouble understanding the standard security questions, and she had to go over them slowly until they gave the routine, reassuring answers.

    Their flight was scheduled to depart at 8:00.

    The security checkpoints through which passengers, including Atta and his colleagues, gained access to the American 11 gate were operated by Globe Security under a contract with American Airlines. In a different terminal, the single checkpoint through which passengers for United 175 passed was controlled by United Airlines, which had contracted with Huntleigh USA to perform the screening.

    In passing through these checkpoints, each of the hijackers would have been screened by a walk-through metal detector calibrated to detect items with at least the metal content of a .22-caliber handgun. Anyone who might have set off that detector would have been screened with a hand wand-a procedure requiring the screener to identify the metal item or items that caused the alarm. In addition, an X-ray machine would have screened the hijackers' carry-on belongings. The screening was in place to identify and confiscate weapons and other items prohibited from being carried onto a commercial flight.

    None of the checkpoint supervisors recalled the hijackers or reported anything suspicious regarding their screening.

    While Atta had been selected by CAPPS in Portland, three members of his hijacking team-Suqami, Wail al Shehri, and Waleed al Shehri-were selected in B
    911report/chapter-1.txt
```



**Example 2:**


*Command:*

```
less -E 911report/chapter-2.txt
```

*Output:*

```

```


*Source:*
[Link](https://phoenixnap.com/kb/less-command-in-linux)

---

2) Option 2

`-N` 

**Example 1:**

*Command:*

```
less -N 911report/chapter-1.txt
```

*Output:*

```
                                                                                                                    
```



**Example 2:**

*Command:*

```
less -N 911report/chapter-1.txt
```

*Output:*

```

```



*Source:*
[Link](https://www.geeksforgeeks.org/less-command-linux-examples/)

---

3) Option 3

`-X`

**Example 1:**

*Command:*

```
less -X 911report/chapter-1.txt
```

*Output:*

```

```

**Example 2:**


*Command:*

```
less -X 911report/chapter-1.txt
```

*Output:*

```

```

*Source:*
[Link](https://phoenixnap.com/kb/less-command-in-linux)

---

4) Option 4

`-p`

**Example 1:**

*Command:*

```
less -p  911report/chapter-1.txt
```

*Output:*

```

```



**Example 2:**


*Command:*

```
less -p  911report/chapter-1.txt
```

*Output:*

```

```



*Source*:
[Link](https://www.geeksforgeeks.org/less-command-linux-examples/)

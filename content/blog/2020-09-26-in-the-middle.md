<!-- title: In the Middle? -->

## Earlier attempts

```java
public boolean xyzMiddle(String str) {
 int last_check = -1;
 while (true) {
  int value = str.indexOf("xyz", last_check + 1);
  if (value == -1)
   return false;
  String left_sub = str.substring(0, value);
  int no_left = left_sub.length();
  String right_sub = str.substring(value + 3, str.length());
  int no_right = right_sub.length();
  if (Math.abs(no_left - no_right) <= 1) {
   return true;
  } else {
   last_check = value;
  }
 }
}
```

### 2nd attempt
```java
public boolean xyzMiddle(String str) {
  int len_s = str.length();
  if (len_s < 3) 
    return false; 
  int mid = len_s/2-1;
  int start = mid;
  if (len_s % 2 == 0) start -= 1; 
  int end = mid + 3; 
  return str.substring(start,end).contains("xyz");
}
```



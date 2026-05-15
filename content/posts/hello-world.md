+++
title = "Hello World"
date = "2026-05-15T10:40:37+02:00"
#dateFormat = "2006-01-02" # This value can be configured for per-post date formatting
author = "Kasra Madadipouya"
authorTwitter = "kasra_mp" #do not include @
cover = ""
tags = ["test", "hello-world"]
keywords = ["test", "hello world"]
description = "First post for test"
showFullContent = false
readingTime = false
hideComments = false
+++

## Introduction

This is a test page that will not be up for a long time. The intention is just
to ensure the website works and the post renders well.

### How to know?

It's simple and easy. Just deploy the website and if everything works fine, means
everything is working as expected. Otherwise, it's not :-D

Another approach is to get the source code of the page in browser and go through
it to see whether everything is in place. Actually it's a matter of trial and
error at the end of the day.

### Custom code

Let's write a simple C program here, in drop down:

{{< code language="c" title="Really cool snippet" open="true" >}}

#include <stdio.h>
#include <stdlib.h>

int main(int argc, char* argv[])
{
  printf("Hello World\n");
  return 0;
}
{{< /code >}}

The same code in one shot:

```c
#include <stdio.h>
#include <stdlib.h>

int main(int argc, char* argv[])
{
  printf("Hello World\n");
  return 0;
}
```
And now some Java code:

```java
public class Test {
  public static void main(String args[]) {
    System.out.println("Helo World");
  }
}
```

And complete it with a picture:

{{< image
    src="/images/hello.jpg"
    alt="Hello Friend"
    position="center"
    style="border-radius: 8px;"
>}}

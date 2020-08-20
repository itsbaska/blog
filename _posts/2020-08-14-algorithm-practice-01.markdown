---
layout: post
title: "01. Algorithm Practice"
date: 2020-08-14 20:34:06 -0600
categories: algorithm practice
---

Solving algorithms quickly is not my strongest point. But I am hoping with repeat practice I will get better at it.

The first pattern that I wanted to solidify is the Sliding Window pattern. So here is a simple example:

**Given an array, find the average of all contiguous subarrays of size ‘S’ in it.**

Input:

```ruby
numbers = [1, 3, 2, 6, -1, 4, 1, 8, 2]
s = 5
```

Expected Output:

```ruby
[2.2, 2.8, 2.4, 3.6, 2.8]
```

The subsets would looks something like this:

```ruby
[1, 3, 2, 6, -1]
[3, 2, 6, -1, 4]
[2, 6, -1, 4, 1]
[6, -1, 4, 1, 8]
[-1, 4, 1, 8, 2]
```

| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **1** | **3** | **2** | **6** | **-1**| 4 | 1 | 8 | 2 |
| 1 | **3** | **2** | **6** | **-1**| **4** | 1 | 8 | 2 |
| 1 | 3 | **2** | **6** | **-1**| **4** | **1** | 8 | 2 |
| 1 | 3 | 2 | **6** | **-1**| **4** | **1** | **8** | 2 |
| 1 | 3 | 2 | **6** | **-1**| **4** | **1** | **8** | **2** |

The averages of these subsets would be:

```ruby
[1, 3, 2, 6, -1] # => 2.2
[3, 2, 6, -1, 4] # => 2.8
[2, 6, -1, 4, 1] # => 2.4
[6, -1, 4, 1, 8] # => 3.6
[-1, 4, 1, 8, 2] # => 2.8
```

Here is the simplest example of this pattern

```ruby
def sliding_average(size, array)
  averages = []
  array.each_with_index do |num, window_start|
    window_end = window_start + size - 1
    subset = array[window_start..window_end]
    averages << subset.sum / size.to_f
    break if window_start == size - 1
  end
  averages
end
```

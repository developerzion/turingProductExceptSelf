## **Turing Challenge: ProductExceptSelf using PHP**

Given an array **nums** of n integers where n>1, return an array **output** such that **output[i]** is equal to the product of all the elements of **nums** except **nums[i]**

**Example:**

```php
Input:** [1,2,3,4]
```

**Output: [24,12,8,6]** 

Note Please solve it without using division and in O(n)

```php
class Solution{
	function productExceptself($nums){
		$arr = array();
		$f_loop = 1;
		$s_loop = 1;
		for ($i=0; $i <count($nums); $i++) { 
			$arr[$i] = $f_loop;
        	$f_loop = $f_loop * $nums[$i];	
		}
	    for($i=count($nums)-1; $i>=0; $i--){
	        $arr[$i] = $s_loop * $arr[$i];
	        $s_loop = $s_loop * $nums[$i];
	    }
	    return $arr;
	}
}

$nums = [1,2,3,4];
$solution = new Solution();
$output = $solution->productExceptself($nums);
echo '['. implode(",", $output). ']';
```
```php
Output: [24,12,8,6]
```
# Daily-Coding-Problem-And-Solution

# Problem 1
Given a list of numbers and a number k, return whether any two numbers from the list add up to k.

For example, given `[10, 15, 3, 7]` and k of `17`, return true since `10 + 7 is 17`.

### Example 1:

Input: nums = `[10, 15, 3, 7]`, key = `17`
Output: `true`

### Example 2:

Input: nums = `[10, 15, 3, 7]`, key = `5`
Output: `false`

## Solution

```
#include <iostream>;

using namespace std;

bool twoSum(int *a, int key, int length)
{
    bool found = false;

    for(int i = 0; i <length; i++)
    {
        for(int j = i+1; j<length; j++)
        {
            if(a[i]+a[j]==key)
            {
                found=true;
                break;
            }
        }

        if(found)
        {
            break;
        }
    }

    return found;
}

int main()
{
    int a[] = {10, 15, 3, 7};
    int key = 17;
    int length = sizeof(a)/sizeof(a[0]);

    cout << boolalpha << twoSum(a, key, length) << endl;

    return 0;
}


```

# Problem 2
Given an array of integers, return a new array such that each element at index `i` of the new array is the product of all the numbers in the original array except the one at `i`.

For example, if our input was `[1, 2, 3, 4, 5]`, the expected output would be `[120, 60, 40, 30, 24]`. If our input was `[3, 2, 1]`, the expected output would be `[2, 3, 6]`.

## Solution

```

#include <iostream>
#include <vector>
using namespace std;

vector<int> productExceptSelf(vector<int>& nums)
{
    int vSize = nums.size();
    vector<int> result(vSize, 1);

    for(int i = 0; i < vSize; i++)
    {
        for(int j = 0; j < vSize; j++)
        {
            if(i!=j)
            {
                result[i] = result[i] * nums[j];
            }
        }
    }

    return result;
}

void printArray(vector<int> a)
{
    for(unsigned int i = 0; i < a.size(); i++)
    {
        cout << a[i] << " ";
    }
}

int main()
{
    vector<int> nums = {1, 2, 3, 4, 5};
    printArray(productExceptSelf(nums));

    return 0;
}

```

# Problem 3
Print duplicate characters from String

## Solution

```
#include <iostream>
#include <map>

using namespace std;

void printDupChar(string str)
{
    map<char, int> count;
    for (int i = 0; i < str.length(); i++)
    {
        count[str[i]]++;
    }

    for (auto it : count)
    {
        if (it.second > 1)
            cout << it.first << ", count = " << it.second << "\n";
    }
}

int main()
{
    string str = "Java";
    printDupChar(str);

    return 0;
}

```

# Problem 4
Check if two Strings are anagrams of each other?

## Solution

```
#include <iostream>
#include <algorithm>
using namespace std;

bool twoStringAnagrams(string &str1, string &str12)
{
    if(str1.length()!=str12.length())
        return false;

    sort(str1.begin(), str1.end());
    sort(str12.begin(), str12.end());

    if(str1!=str12)
        return false;

    return true;
}


int main()
{
    string str1 = "abcd";
    string str2 = "dcbas";

    if(twoStringAnagrams(str1,str2))
    {
        cout << "The two strings are anagram of each other";
    }
    else
    {
        cout << "The two strings are not anagram of each other";
    }

    return 0;
}

```

# Problem 5
Print the first non-repeated character from String

## Solution

```
#include <iostream>
#include <map>

using namespace std;

void firstNonRepeatedChar(string str)
{
    map<char, int> count;
    for (int i = 0; i < str.size(); i++)
    {
        count[str[i]]++;
    }

    for (auto it : count)
    {
        // cout << it.first << " " << it.second << endl;

        if (it.second == 1)
        {
            cout << "First non-repeating character is: " << it.first << " ";
            break;
        }
    }
}

int main()
{
    string str = "ShohelRana";
    firstNonRepeatedChar(str);

    return 0;
}

```
# Problem 6
Reverse a given String using recursion

## Solution

```
#include <iostream>

using namespace std;

void reverse(string str)
{
    if(str.size() == 0)
    {
        return;
    }

    reverse(str.substr(1));
    cout << str[0];
}

int main()
{
    reverse("shohel");
    return 0;
}

```
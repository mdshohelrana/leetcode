# Daily-Coding-Problem-And-Solutiion

# Problem
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

bool twoSum(int a[], int key)
{
    bool found = false;

    for(int i = 0; i <sizeof(a); i++)
    {
        for(int j = i+1; j<sizeof(a); j++)
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

    cout << boolalpha << twoSum(a, key) << endl;

    return 0;
}

```
#Answer For Question 1

import functools

def countDistinct(s):

	m = {}

	for i in range(len(s)):

		if s[i] not in m:
			m[s[i]] = 1
		else:
			m[s[i]] += 1

	return len(m)

def compare(a, b):
	
	if (countDistinct(a) == countDistinct(b)):
		return (len(b) - len(a))
	else:
		return (countDistinct(a) - countDistinct(b))

arr = [ "I", "like", "to",
		"dance" ]

n = len(arr)

print(*sorted(
	arr, key = functools.cmp_to_key(compare)), sep = ' ')
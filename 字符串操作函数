
/****由于在学习中的一点小问题，就把字符串的库函数以及内存拷贝函数拿出来自己实现一下，加深理解****/

#include <stdio.h>
#include <assert.h>
#include <stdlib.h>

char* my_strcpy(char* dst,const char* src)
{
	assert(dst);
	assert(src);

	char *ret = dst;  //把首地址保存起来，因为下面会修改dst
	while (*dst++ = *src++)
		;

	return ret;
}

char* my_strncpy(char* dst,const char* src,int n)
{
	assert(dst);
	assert(src);

	char* ret = dst;
	while (n--)
	{
		*dst++ = *src++;
	}

	return ret;
}


char* my_strcat(char* dst,const char* src)
{
	assert(dst);
	assert(src);

	char *ret = dst;

	while (*dst) 
		dst++;

	while (*dst++ = *src++)
		;

	return ret;
}

char* my_strncat(char *dst, const char *src, int n)
{
	assert(dst);
	assert(src);

	char *ret = dst;
	while (*dst)
		dst++;
	while (n--)
	{
		*dst++ = *src++;
	}

	return ret;
}

int my_strcmp(const char* dst,const char* src)
{
	assert(dst);
	assert(src);

	while ((*dst == *src) && *dst && *src)
	{
		dst++;
		src++;
		if (*dst == 0 && *src == 0)
		{
			return 1;
		}
	}

	return -1;
}

int my_strncmp(char* dst, const char* src, int n)
{
	assert(dst);
	assert(src);

	while (n--)
	{
		if ((*dst == *src) && *dst && *src)
		{
			dst++;
			src++;
		}
		else
		{
			return -1;
		}

		if (*dst == 0 && *src == 0) // 全部相同时的处理情况
		{
			return 1;
		}
	}	

	return 1; // 部分相同时的处理情况
}

char* my_strstr_1(char* str1, char* str2)
{
	assert(str1); // 原串
	assert(str2); // 子串

	char* s1 = str1;
	char* s2 = str2;
	char* s = str2; // 保存子串的首地址

	if (*s1 == 0)
	{
		if (*s2)
			return NULL;

		return s;
	}

	while (*s1 && *s2)
	{
		if (*s1 != *s2)
		{
			s1++;
		}
		if (*s1 == *s2)
		{
			s1++;
			s2++;
		}
		if (*s1 != *s2)
		{
			if (*s1 == 0)
			{
				return NULL;
			}
			else if (*s2 == 0)
			{
				return s;
			}

			s2 = s;
		}	
	}

	return NULL;
}

char* my_strstr_2(char* dest, char* src)
{
	assert(src);
	assert(dest);

	char* s1 = dest;  //s1与s2控制src,dest往下走
	char* p = s1;    //p是else中方便保存的下一个字符
	char* s2 = src;

	while (*s1)
	{
		p = s1;  //else中保存的下一个字符
		s2 = src;
		while (*s1 && *s2)
		{
			if (*s1 == *s2)
			{
				s1++;
				s2++;
			}

			//不相等则将arr1向下走一个字符，再开始比较是否相等
			else
			{
				s1++;
				break;
			}
		}

		if (*s2 == '\0')    //相等，返回
		{
			return s1;
		}
	}
	return NULL;
}


void* my_memcpy(void *dst,const void *src,size_t count)
{
	assert(dst);
	assert(src);

	char *pDst = (char*)dst;
	char *pSrc = (char*)src;
	char *ret = (char*)dst; // 保存dst首地址

	while (count--)
	{
		*pDst++ = *pSrc++;
	}

	return ret;
}

void* my_memmove(void *p1,void *p2,size_t count)
{
	// 在一个数组中进行
	assert(p1);
	assert(p2);

	char *dst = (char*)p1;
	char *src = (char*)p2;
	char *ret = (char*)p1; // 保存首地址

	if (dst > src && (dst < src + count)) // 判断内存重叠情况
	{
		while (count--)
		{
			*(dst + count) = *(src + count);
		}
	}
	else // 不重叠情况
	{
		while (count--)
		{
			*dst++ = *src++;
		}
	}

	return ret;
}

void* my_memset(void* arr,int c,size_t size)
{
	assert(arr);

	char* dst = (char*)arr;
	int i = 0;
	for (i = 0; i < size; i++)
	{
		*(dst + i) = c;
	}

	return arr;
}


void test1()
{
	char a1[10] = { 0 };
	char a2[] = "world";

	printf("%s", my_strcpy(a1, a2));
	printf("\n");
}


void test2()
{
	char a1[15] = "hello";
	char a2[] = " world";

	printf("%s",my_strcat(a1,a2));
	printf("\n");
}


void test3()
{
	char a1[] = "abcdef";
	char a2[] = "abcdef";
	printf("%d\n",my_strcmp(a1,a2));
}


void test4()
{
	char a1[10] = "hello";
	char a2[] = " world";

	printf("%s",my_strncat(a1,a2,4));
	printf("\n");
}


void test5()
{
	int a1[10] = {1,2,3,4,5,6,7,8,9,10};
	int a2[10];
	int i = 0;

	my_memcpy(a2,a1,4);
	for (i = 0; i < 10;i++)
	{
		printf("%d ", a2[i]);
	}
	printf("\n");
}


void test6()
{
	int a[10] = {1,2,3,4,5,6,7,8,9,10};
	int i = 0;

	my_memmove(a+2,a+5,4);
	for (i = 0; i < 10;i++)
	{
		printf("%d ",a[i]);
	}
	printf("\n");
}


void test7()
{
	char a1[10] = { 0 };
	char a2[] = "world";

	printf("%s", my_strncpy(a1, a2, 3));
	printf("\n");
}


void test8()
{
	char a1[] = "abcdef";
	char a2[] = "acb";

	printf("%d\n", my_strncmp(a1, a2, 2));
}


void test9()
{
	char* a1 = "abccddefgh";
	char* a2 = "cddef";

	printf("%s",my_strstr_1(a1,a2));
	printf("\n");

	printf("%s", my_strstr_2(a1, a2));
	printf("\n");
}


void test10()
{
	int arr[10];
	int i = 0;
	my_memset(arr, 0, 32);
	for (i = 0; i < 10; i++)
		printf("%d ",arr[i]);
	printf("\n");
}

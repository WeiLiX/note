所有的警告都是错误.

gcc/g++ 编译警告选项:

` -Wall -Wextra`

官方: <http://gcc.gnu.org/onlinedocs/gcc/Warning-Options.html>


`-Werror`

所有警告强制升级为错误提示

`-Wpedantic`    
`-pedantic `

Issue all the warnings demanded by strict ISO C and ISO C++.

`-pedantic-errors`
	
`-pedantic ` Warning to Error.

` -Wall`

我们平时可能大多数情况只使用-Wall编译警告选项，实际上-Wall选项是一系列警告编译选项的集合。

-Wall turns on the following warning flags:

          -Waddress   
          -Warray-bounds (only with -O2)  
          -Wc++11-compat  
          -Wchar-subscripts  
          -Wenum-compare (in C/ObjC; this is on by default in C++) 
          -Wimplicit-int (C and Objective-C only) 
          -Wimplicit-function-declaration (C and Objective-C only) 
          -Wcomment  
          -Wformat   
          -Wmain (only for C/ObjC and unless -ffreestanding)  
          -Wmaybe-uninitialized 
          -Wmissing-braces (only for C/ObjC) 
          -Wnonnull  
          -Wparentheses  
          -Wpointer-sign  
          -Wreorder   
          -Wreturn-type  
          -Wsequence-point  
          -Wsign-compare (only in C++)  
          -Wstrict-aliasing  
          -Wstrict-overflow=1  
          -Wswitch  
          -Wtrigraphs  
          -Wuninitialized  
          -Wunknown-pragmas  
          -Wunused-function  
          -Wunused-label     
          -Wunused-value     
          -Wunused-variable  
          -Wvolatile-register-var 

-Wextra 

	-Wall扩展版
        -Wclobbered  
          -Wempty-body  
          -Wignored-qualifiers 
          -Wmissing-field-initializers  
          -Wmissing-parameter-type (C only)  
          -Wold-style-declaration (C only)  
          -Woverride-init  
          -Wsign-compare  
          -Wtype-limits  
          -Wuninitialized  
          -Wunused-parameter (only with -Wunused or -Wall) 
          -Wunused-but-set-parameter (only with -Wunused or -Wall)  
## -Wcomment (-Wall)

## -Wshadow
当局部变量遮蔽(shadow)了参数、全局变量或者是其他局部变量时，该警告选项会给我们以警告信息。例如:
```
// test_shadow.c
int g;
int main(int argc,char **argv)
{
        short   i;
        double  g;
	retrun 0;
}
```
##inline
-Winline 让 gcc 对标志成 inline 但不能被替换的函数给出警告信息以及不能替换的原因。如下面例子，它使用了可变长度数据类型变量作为参数：
```
inline int func(int *a)
{
    int c = 4;
    char p[c]; /* 可变长度数组 */
    (*a)++;
}
/*
 * 测试函数： 使用 gcc -Winline ... 来提示信息
 */
int main(void)
{
    int d = 1;
    func(&d);
    return 0;
}
```
## -Wpacked -Wpadded 
检测结构体内存对齐/手动packed提示效率问题,自动padded也有提示.

## -Wunreachable-code
不可到达的代码
## -Woverloaded-virtual

-Wmissing-include-dirs

## -Wundef


#参考资料:
1. <http://hi.baidu.com/asgznnuavmbsuzq/item/e6da157aaead3714d1dcb357>
2. <http://www.blogjava.net/ivanwan/archive/2005/08/04/9338.html>
3. <http://fengyongcheng1985.blog.163.com/blog/static/115925435201191722426925/>
4. <http://3y.uu456.com/bp-2b96985077232f60dccca105-3.html>

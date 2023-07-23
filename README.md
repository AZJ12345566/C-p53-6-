# C-p53-6-
C语言学习笔记 p53 内存操作函数讲解(6)
#include<stdio.h>
#include<string.h>
void* my_memcpy(void* dest,const void* src,size_t count)
{
    char* ret=dest;
    assert(dest!=NULL);
    assert(src!=NULL);
    
    while(count--)
    {
        *(char*)dest=*(char*)src
        ++(char*)dest;
        ++(char*)src;
    }
    return ret;
}


void* my_memmove(void* dest,const void*src,size_t count)
{
    void* ret=dest;
    assert(dest!=NULL);
    assert(src!=NULL);
    if(dest<src)
    {
        //前->后
        while(count--)
        {
            *(char*)dest=*(char*)src;
            ++(char*)dest;
            ++(char*)src;
        }
    }
    else
    {
        //后->前
        while(count--)
        {
            *((char*)dest+count)=*((char*)src+count;
        }
    }
    return ret;
}

int main()
{
    int arr1[]={1,2,3,4,5};
    int arr2[10]={0};
    //arr1中的数字拷贝到arr2中
    //my_memcpy(arr2,arr1,20);

    int arr3[]={1,2,3,4,5,6,7,8,9,10};
    memmove(arr3+2,arr3,20);//可以实现重叠拷贝
    return 0;
}


int main()
{
    int arr1[]={1,2,3,4,5};
    int arr2[]={1,2,5,4,3};
    int ret=memcmp(arr1,arr2,8);//这里的8是指字节数
    printf("%d\n",ret);
    return 0;
}


//memset-内存设置
int main()
{
    char arr[10]="";
    memset(arr,'#',10);//这里也是字节
    return 0;
}

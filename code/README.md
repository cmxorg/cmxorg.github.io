# Windows_API CreateFile and WriteFile code
## Windows_API_Boot.cs
```
using System;
using System.Runtime.InteropServices;
namespace MBR
{
    public class Boot
    {
        [DllImport("kernel32.dll",SetLastError = true)]                        //调用kernel32.dll组件
        public static extern IntPtr CreateFileA(string lpFileName,uint dwDesiredAccess,uint dwShareMode,uint lpSecurityAttributes,uint dwCreationDisposition,uint dwFlagsAndAttributes,IntPtr hTemplateFile);                    //调用外部命令
        [DllImport("kernel32.dll",SetLastError = true)]                        //调用kernel32.dll组件
        public static extern bool WriteFile(int hFile, byte[] lpBuffer, int nNumberOfBytesToWrite, ref int lpNumberOfBytesWritten, IntPtr lpOverlapped);                                                 //调用外部命令
        const int File_Share_Read=0x00000001;             //部分参数的值
        const int File_Share_Write=0x00000002;
        const uint Generic_Read = 0x80000000;
        const uint Generic_Write = 0x40000000;
        const int Open_Existing = 3;
    }
} 
```

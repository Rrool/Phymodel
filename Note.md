# Note 一些OpenGL开发过程的笔记

## 一、OpenGL配置过程中

### 1.按教程更改为x64位编码

https://athena.ecs.csus.edu/~gordonvs/C1Elibraries.html

### 2.编译书本示范程序时发生错误

https://github.com/bincrafters/community/issues/126

解决方案：my suggestion is to use /Z7 option instead of /Zi when building glfw as static library - this way debugging information is embedded into library and pdb files are not needed

https://stackoverflow.com/questions/284778/what-are-the-implications-of-using-zi-vs-z7-for-visual-studio-c-projects

https://docs.microsoft.com/en-us/cpp/build/reference/z7-zi-zi-debug-information-format?view=msvc-160

### 3.从书本2.5程序开始输出全部红色

解决：书中代码部分漏掉了填充缓冲区的代码，需要补上：

```C
    glClear(GL_DEPTH_BUFFER_BIT);
    glClearColor(0.0, 0.0, 0.0, 1.0);
    glClear(GL_COLOR_BUFFER_BIT);
```


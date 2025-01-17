# 任务四：ArceOS + 网卡驱动 in Qemu for AArch64/RISC-V 验证

1.  配置
    

      ```shell
      # qemu目录下
      sudo apt-get install libslirp-dev
      sudo apt install flex
      sudo apt install bison
      ./configure --target-list=aarch64-softmmu --enable-slirp    //AArch64
      ./configure --target-list=riscv64-softmmu --enable-slirp    //RISC-V
      ```

 ![picture](assert/task1.4.1.png)

2.  编译
      
      ```shell
      make
      ```

![picture](assert/task1.4.2.png)

3.  运行

      ```shell
      # arceos目录下
      make A=apps/net/httpserver ARCH=aarch64 LOG=info NET=y SMP=4 run  // AArch64
      make A=apps/net/httpserver ARCH=riscv64 LOG=info NET=y SMP=4 run  // RISC-V
      ```
    
![picture](assert/task1.4.3.png)

成功后显示得到的网址

![picture](assert/task1.4.4.png)

访问localhost:(端口号)，得到:

![picture](assert/task1.4.5.png)

同时终端更新Log:

![picture](assert/task1.4.6.png)
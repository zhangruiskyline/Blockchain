1. 如果已经安装unbuntu16.04 请跳至 第6步骤.
2. 如果对于homebrew非常熟悉的mac用户可以自行编译,否则执行第3步骤
  2.1. 参考  https://github.com/ethereum/go-ethereum/wiki/Installation-Instructions-for-Mac

3. 对于windows/macos 用户  请根据自己的情况 选择安装  vmware player 或者 vmware fusion 或者 virtualbox 或者 parallels
4. 下载 http://releases.ubuntu.com/16.04/ubuntu-16.04.4-desktop-amd64.iso
5. 在已经安装好的虚拟机上 安装 ubuntu 16.04
6. 安装结束后,  运行  sudo apt-get update
7. 接着运行如下指令
  1. sudo add-apt-repository ppa:gophers/archive
  2. sudo apt-get update
  3. sudo apt install  -y  build-essential  golang-1.9-go golang-1.9-doc  software-properties-common  openssh-server
  4. sudo apt install  -y  libdb++-dev   libssl-dev  libreadline-dev  autoconf  curl wget
  5. echo "export PATH=$PATH:/usr/lib/go-1.9/bin/" >> ~/.bashrc
  6. source ~/.bashrc (安装openssh server之后用putty可以远程登录上去, 而不用在vm的界面上操作)
  7. go  version   确认版本号是1.9  正确的话应该看到 "go version go1.9.4 linux/amd64"
  8. git clone  https://github.com/ethereum/go-ethereum.git
  9. cd  go-ethereum
  10. 运行 "make  geth"  应该是可以building 成功 (必须要保证网络连通互联网, 这个building过程需要去github下载geth依赖的go package)
  11. 结束后 可以看到
    1. Done building.
    2. Run "/home/Path_To/geth" to launch geth.
                           运行  "Path_to/geth"  version  应该会看到如下输出
                             注意这里的 "Path_to" 是指你自己的路径,需要替换为你自己的路径
    3. Geth
    4. Version: 1.8.2-unstable
    5. Git Commit: 66cd41af1e3827f9f834ca6ea98d6964d2388f77
    6. Architecture: amd64
    7. Protocol Versions: [63 62]
    8. Network Id: 1
    9. Go Version: go1.9.4
    10. Operating System: linux

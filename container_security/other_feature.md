##其它内核安全特性
Capabilities是现代linux内核提供的诸多安全特性中的一个，Docker可以利用现有的如TOMOYO, AppArmor, SELinux, GRSEC来增强安全性。

为什么Docker当前只启用capabilities,而不介入其他系统。
因为这样就可以有很多方法来加固Docker主机，下面是一些例子。
* 可以在内核中加载GRSEC和PAX，这会增加很多安全检查。
* 可以使用一些有增强安全特性的发行版的模板，比如带apparmor的模板和redhat系列带selinux dcoker策略，这些模板提供了额外的安全特性。
* 使用你自己喜欢的访问控制机制来定义你自己的安全策略。
像其他添加到docker容器的第三方工具一样（比如网络拓扑和文件系统共享），有很多这样的工具，利用他们可以不用改变docker内核就可以加固现有的docker容器

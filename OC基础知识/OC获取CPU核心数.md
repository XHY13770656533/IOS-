# OC 获取CPU核心数



获取CPU核心数目的OC代码。

```objective-c
#include <sys/sysctl.h>
 
unsigned int countOfCores()
{
    unsigned int ncpu;
    size_t len = sizeof(ncpu);
    sysctlbyname("hw.ncpu", &ncpu, &len, NULL, 0);
    //当前电源管理模式下可用的物理处理器数量。
  	//sysctlbyname("hw.physicalcpu", &ncpu, &len, NULL, 0);
  	//此引导中可用的最大物理处理器数。
  	//sysctlbyname("hw.physicalcpu_max", &ncpu, &len, NULL, 0);
  	//当前电源管理模式下可用的逻辑处理器数量。
  	//sysctlbyname("hw.logicalcpu", &ncpu, &len, NULL, 0);
  	//可用于此引导的最大逻辑处理器数。
  	//sysctlbyname("hw.logicalcpu_max", &ncpu, &len, NULL, 0);
    return ncpu;

}
```


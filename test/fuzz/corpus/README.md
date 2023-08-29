# Corpra for fuzz tests with fixed API calls scenarios
These corpra contain UR API calls in a predefined order described below.
All scenarios begin with single calls to urInit() and urAdapterGet().

## create-release
Test device/context/pool create and release

urPlatformGet()
urPlatformGet()
urDeviceGet()
urDeviceGet()
urDeviceRelease()
urDeviceGet()
urDeviceGet()
urContextCreate()
urContextRelease()
urContextCreate()
urUSMPoolCreate()
urUSMPoolCreate()
urUSMPoolRelease()
urUSMPoolRelease()
urUSMPoolCreate()
urUSMPoolCreate()
urUSMPoolCreate()
urUSMPoolCreate()
urUSMPoolRelease()
urUSMPoolRelease()
urUSMPoolRelease()
urUSMPoolRelease()
urContextRelease()

## pool-alloc
Allocate with host and device pools

urPlatformGet()
urPlatformGet()
urDeviceGet()
urDeviceGet()
urContextCreate()
urUSMPoolCreate()
urUSMPoolCreate()
urUSMPoolCreate()
urUSMPoolCreate()
urUSMHostAlloc()
urUSMDeviceAlloc()
urUSMFree()
urUSMPoolRelease()
urUSMPoolRelease()
urUSMFree()
urUSMPoolRelease()
urUSMPoolRelease()
urContextRelease()

## alloc
Allocate on host/device, no pools

urPlatformGet()
urPlatformGet()
urDeviceGet()
urDeviceGet()
urContextCreate()
urUSMHostAlloc()
urUSMDeviceAlloc()
urUSMFree()
urUSMFree()
urContextRelease()

## kernel-launch
Launch kernel

urPlatformGet()
urPlatformGet()
urDeviceGet()
urDeviceGet()
urContextCreate()
urProgramCreateWithIL()
urProgramBuild()
urKernelCreate()
urQueueCreate()
urEnqueueKernelLaunch()
urEventWait()
urEventRelease()
urQueueFinish()
urQueueRelease()
urKernelRelease()
urProgramRelease()
urContextRelease()
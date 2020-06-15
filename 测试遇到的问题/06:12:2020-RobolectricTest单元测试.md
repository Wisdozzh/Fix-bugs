# 问题1 java.lang.VerifyError: Expecting a stackmap frame at branch target 27
- 日期：20/1206/2020
- 简述：VerifyError
- 详细描述 如下：

```
java.lang.VerifyError: Expecting a stackmap frame at branch target 27
Exception Details:
  Location:
    com/umeng/commonsdk/UMConfigure.invoke(Ljava/lang/reflect/Method;Ljava/lang/Object;[Ljava/lang/Object;)V @1: ifnull
  Reason:
    Expected stackmap frame at this location.
  Bytecode:
    0x0000000: 2ac6 001a 2bc6 0016 2a2b 2cb6 00c1 57a7
    0x0000010: 000c 4ea7 0008 4ea7 0004 4eb1          
  Exception Handler Table:
    bci [8, 15] => handler: 18
    bci [8, 15] => handler: 22
    bci [8, 15] => handler: 26


	at com.ireadabc.iteachabc.App.initUMENG(App.java:55)
	at com.ireadabc.iteachabc.App.onCreate(App.java:34)
	at org.robolectric.android.internal.AndroidTestEnvironment.lambda$installAndCreateApplication$0(AndroidTestEnvironment.java:276)
	at org.robolectric.util.PerfStatsCollector.measure(PerfStatsCollector.java:75)
	at org.robolectric.android.internal.AndroidTestEnvironment.installAndCreateApplication(AndroidTestEnvironment.java:276)
	at org.robolectric.android.internal.AndroidTestEnvironment.setUpApplicationState(AndroidTestEnvironment.java:169)
	at org.robolectric.RobolectricTestRunner.beforeTest(RobolectricTestRunner.java:301)
	at org.robolectric.internal.SandboxTestRunner$2.lambda$evaluate$0(SandboxTestRunner.java:243)
	at org.robolectric.internal.bytecode.Sandbox.lambda$runOnMainThread$0(Sandbox.java:89)
	at java.util.concurrent.FutureTask.run(FutureTask.java:266)
	at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1149)
	at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:624)
	at java.lang.Thread.run(Thread.java:748)

```
- 去找解决方法:去stackoverflow上面搜索
地址：https://stackoverflow.com/questions/26733946/java-lang-verifyerror-expecting-a-stackmap-frame-at-branch-target

- 解决方案：在运行测试上面编辑配置“Edit Configurations” -> 选中对应的单元测试 -> 有一个“VM options：” -	> 在“-ea”后面添加“ -noverify”

# 问题2



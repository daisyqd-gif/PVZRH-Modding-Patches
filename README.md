**Patch 1:
***Error:
[Error  :Il2CppInterop] During invoking native->managed trampoline
Exception: System.Security.VerificationException: Method System.Runtime.CompilerServices.AsyncTaskMethodBuilder.AwaitOnCompleted: type argument 'Cysharp.Threading.Tasks.UniTask+Awaiter' violates the constraint of type parameter 'TAwaiter'.
***Fix:
Drag the regenerated UniTask.dll from the release folder
**Patch 2:
***Error:
***Patch:

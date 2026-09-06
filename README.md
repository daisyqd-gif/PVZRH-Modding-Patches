# Daignosing errors:
1. Game crashing
  1. Enter the BepInEx folder and open the ErrorLog.log file in any text editor.
  2. You should see the specific error.
  3. Find the error below in the fixes section and fix it.
2. Something feels wrong:
  1. Open the black BepInEx window..
  2. Scroll up and find red error logs.
  3. Ignore these errors:
```diff
- Assembly xxx is not registered to il2cpp
- [UniverseLib] THIS WARNING IS NOT BUG!!!! DON'T REPORT THIS!!!!!
- System.TypeLoadException: GenericArguments[0], 'xxxDebuff', on 'BaseBuff`1[T]' violates the constraint of type parameter 'T'.
- During invoking native->managed trampoline
- Exception: System.NullReferenceException: Object reference not set to an instance of an object.
-    at CustomizeLib.BepInEx.Patch.TravelPackagePatch.PostInit(TravelPackage __instance)
- Warnings
  4. Try including the PDB in the mod and find the line number.
  5. Find the error below in the fixes section and fix it.
```
# Fixes:
## Patch 1:
### Error:
```diff
-[Error  :Il2CppInterop] During invoking native->managed trampoline
-Exception: System.Security.VerificationException: Method System.Runtime.CompilerServices.AsyncTaskMethodBuilder.AwaitOnCompleted:
-     type argument 'Cysharp.Threading.Tasks.UniTask+Awaiter' violates the constraint of type parameter 'TAwaiter'.\
```
### Fix:
```diff
+Drag the regenerated UniTask.dll from the repo into BepInEx's interop folder
```
## Patch 2:
### Error:
```diff
-[Error  :Il2CppInterop] During invoking native->managed trampoline
-Exception: System.NullReferenceException
```
### Patch:
```diff
+Add null checks into your code
```

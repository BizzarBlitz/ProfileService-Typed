# ProfileService-Typed
A recreation of loleris's [ProfileService](https://github.com/MadStudioRoblox/ProfileService), compatible with `--!strict` mode, among other changes

ProfileService: Typed is **NOT ENTIRELY BACKWARDS COMPATIBLE** with the original. Even though you'll mostly be fine if you're doing basic work with Profiles, there are various changes that could break some code out there.

One major change is the replacement of arrays with dictionaries in certain areas, prominently in the GlobalUpdates area

For example, `GlobalUpdates:GetLockedUpdates()` now returns `{{UpdateId = 12345, UpdateData = {["ExampleKey"] = "ExampleValue"}}}` instead of `{{12345, {["ExampleKey"] = "ExampleValue"}}}`

This means that you have to do `local UpdateId = Update.UpdateId` instead of `local UpdateId = Update[1]`, which is much cleaner and a required change to maintain type safety

# Type List:
- ProfileStore
- Profile (As returned by `ProfileStore:LoadProfileAsync()`)
- ViewProfile (As returned by `ProfileStore:ViewProfileAsync()` and `ProfileVersionQuery:NextAsync()`)
- GlobalUpdates
- ProfileVersionQuery

- ScriptSignal
- ScriptConnection

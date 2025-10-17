
A scope-based RAII helper that batches USceneComponent transform updates to avoid redundant expensive operations, and can automatically revert failed moves.

**Problem it solves:**
When modifying a component's transform multiple times in quick succession (e.g., setting location then rotation), each modification triggers expensive operations:
- UpdateBounds()
- MarkRenderTransformDirty()
- Overlap queries
- Physics updates
- Child component updates

**How it works:**
Wraps transform modifications in a scope. All changes are deferred until the destructor runs, performing expensive operations only once with the final transform state.

**Usage:**
```cpp
{
    FScopedMovementUpdate ScopedUpdate(Component, EScopedUpdate::DeferredUpdates);
    Component->SetWorldLocation(NewLocation);
    Component->SetWorldRotation(NewRotation);
    Component->SetWorldScale3D(NewScale);
    // Expensive operations happen here when ScopedUpdate destructs
}
```

**Automatic Move Reversion:**
Can detect blocked/invalid moves and automatically restore the original transform:
```cpp
FScopedMovementUpdate ScopedUpdate(Component, EScopedUpdate::DeferredUpdates);
Component->SetWorldLocation(AttemptedLocation);

if (MoveWasBlocked())
{
    ScopedUpdate.RevertMove(); // Restores original transform
}
// Or let destructor handle it based on internal state
```

**Best used when:**
- Applying multiple transform changes in one frame
- Processing batched movement requests
- Updating transform components (location, rotation, scale) together
- Modifying hierarchies of components
- Tentative moves that may need to be reverted (collision resolution, validation)

**Modes:**
- `DeferredUpdates`: Defers all updates until scope exit (most common)
- `ImmediateUpdates`: Applies updates immediately (rarely needed)
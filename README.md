ANDYDatabaseManager
===================

This is class that helps you aliviate that dirty Core Data boilerplate. Now you can go to your AppDelegate remove all the Core Data related code and replace it with:

``` objc
- (void)applicationWillTerminate:(UIApplication *)application
{
    [[ANDYDatabaseManager sharedManager] persistContext];
}
```

``` objc
// ANDYDatabaseManager.h

@property (strong, nonatomic, readonly) NSManagedObjectContext *mainContext;

+ (ANDYDatabaseManager *)sharedManager;

// Creates a new private context.
+ (NSManagedObjectContext *)privateContext;

// Save mainContext.
- (void)saveContext;

// Called in - (void)applicationWillTerminate:(UIApplication *)application
- (void)persistContext;
```

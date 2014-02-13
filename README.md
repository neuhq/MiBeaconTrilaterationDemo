MiBeaconTrilaterationDemo
=========================

Set the iBeacons in the beaconCoordinates.plist (identify by minor) and get coordinates of iDevice with trilateration like this:

    [MiBeaconTrilaterator trilaterateWithBeacons:foundBeacons done:^(NSString *error, NSArray *coordinates) {
        if ([error isEqualToString:@""])
        {
            float x = [[coordinates objectAtIndex:0] floatValue];
            float y = [[coordinates objectAtIndex:1] floatValue];
        }
        else
        {
            NSLog(@"%@", error);
        }
    }];

MiBeaconTrilaterationDemo
=========================

Set the iBeacons in the beaconCoordinates.plist (identify by minor) and get coordinates of iDevice with trilateration like this:

    [MiBeaconTrilaterator trilaterateWithBeacons:foundBeacons done:^(NSString *error, NSArray *coordinates) {
        if ([error isEqualToString:@""])
        {
            float x = [[coordinates objectAtIndex:0] floatValue];
            float y = [[coordinates objectAtIndex:1] floatValue];
            
            [xyResult setText:[NSString stringWithFormat:@"X: %.1f   Y: %.1f", x, y]];
            [selfView setHidden:NO];
            [selfView setFrame:CGRectMake((x * scaleFactor)-10, (maxY-(y * scaleFactor))-10, 20, 20)];
        }
        else
        {
            NSLog(@"%@", error);
            [xyResult setText:@"unable to trilaterate"];
            [selfView setHidden:YES];
        }
    }];

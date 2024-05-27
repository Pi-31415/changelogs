### To Solve

- Wrong Direction of Haply Translation and Virtual Syringe
- Implement Simplified Procedure
- Haptic Feedback is absent (check mesh)
- Auto Spawn based on initial player position
- Human Material (need to have backface culling)
- Add Audio Instruction
- Take ouut the throwing UI
- Adjust Initial Head Height



The BNO055 sensor annd Unity uses very similar but slightly different coordinate systems (just one flipped axis). Hence, the syringe works for all rotation motion, except spinning it on it's logitudinal axis. I disabled this spinning for now in ```FSRSyringe.cs``` with

  
```cs
// [Pi] - Disable the unwanted rotation along the longitudinal syringe axis 
// Compensate for any unwanted tilt caused by the correction on the Z-axis
Vector3 angles = transform.localEulerAngles;
transform.localRotation = Quaternion.Euler(new Vector3(angles.x, angles.y, 0));  // Assuming the unwanted tilt occurs on the x and y axes
``` 

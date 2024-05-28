### To Solve

- Wrong Spinning Direction on Longitudinal Axis of Syringe
- Wrong Direction of Haply Translation and Virtual Syringe
- Implement Simplified Procedure
- Haptic Feedback is absent (check mesh)
- Auto Spawn based on initial player position
- Human Material (need to have backface culling)
- Add Audio Instruction
- Take ouut the throwing UI
- Adjust Initial Head Height



The BNO055 sensor annd Unity uses very similar but slightly different coordinate systems (just one flipped axis). Hence, the syringe works for all rotation motion, except spinning it on it's logitudinal axis. The correct Quaternion configuration is

  
```cs
                float x = float.Parse(tokens[0]);
                float y = float.Parse(tokens[1]);
                float z = float.Parse(tokens[2]);
                float w = float.Parse(tokens[3]);
                Quaternion targetRotation = new Quaternion(y, -z, -x, w);

                //And Calibrate with the following reference Quaternion
                initialReferenceRotation = Quaternion.Euler(0, 180,0 );
``` 

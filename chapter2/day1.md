# Quest

### Contract Code:

    pub contract JacobTucker {
      pub let is: String

      init () {
        self.is = "the best"
        }
    }

### Script Code:

    import JacobTucker from 0x03
    pub fun main(): String {
     return JacobTucker.is
    }

### Script Result:

![image](https://user-images.githubusercontent.com/9120227/167323847-87875e6a-961c-4300-869f-95a0aa4090b1.png)

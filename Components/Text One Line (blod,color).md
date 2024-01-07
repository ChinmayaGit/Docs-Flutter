Text In OneLine 
---------------
(Blod /Color /Text OnPressed)
```
Text.rich(
            TextSpan(
              text: "Don't have an Account ? ",
              style: TextStyle(color: Colors.black),
              children: <TextSpan>[

                TextSpan(
                  text: 'Sign Up',
                  recognizer: TapGestureRecognizer()
                    ..onTap = () {
                      // Add your navigation or sign-up logic here
                    },
                  style: TextStyle(
                    color: Colors.blueAccent,
                    fontWeight: FontWeight.bold,
                  ),
                ),
              ],
            ),
          ),
```
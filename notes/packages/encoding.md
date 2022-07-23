 
 ### JSON
 
 #### exercises
 
 1. Take input from user and convert to json.
    ```golang
      func createJsonFromUserInput() {
        var name string;
        var address string;

        fmt.Print("Enter a name: ")
        fmt.Scan(&name)
        fmt.Print("Enter a address: ")
        fmt.Scan(&address)
        userDetail := map[string]string{
          "name": name,
          "address": address,
        }
        jsonData, err := json.Marshal(userDetail)
        if (err == nil){
          fmt.Print(string(jsonData))
        }

      }
    ```

# Quick Reference

## Java – Maven

### ReadJson.java
```java
import java.io.FileReader;
import java.io.IOException;

import org.json.simple.parser.ParseException;
import org.json.simple.JSONObject;
import org.json.simple.parser.JSONParser;
public class ReadJson {


    public static void main(String[] args)
            throws IOException, ParseException {

        JSONParser jsonparser = new JSONParser();
        FileReader reader = new FileReader(".\\JSON\\Student.json");
Object obj=jsonparser.parse(reader);
        JSONObject studentobj = (JSONObject) obj;

        String fname = (String) studentobj.get("firstname");
        String lname = (String) studentobj.get("lastname");

        System.out.println("Firstname : " + fname);
        System.out.println("Lastname : " + lname);
    }
}
```

### Student.json
```json
{
    "firstname": "Rishitha",
    "lastname": "YV"
}
```

---

## Docker (3)

### Dockerfile
```dockerfile
FROM tomcat:10.1-jre21

COPY sid.html /usr/local/tomcat/webapps/ROOT/index.html

EXPOSE 8080
```

### Commands
```bash
docker --version
docker ps
docker ps -a
docker images
docker build -t docker-siddarth .
docker run -d -p 4098:8080 --name sid-container docker-siddarth
```

---

## Kubernetes (4)

### Commands
```cmd
kubectl config current-context
kubectl get nodes
type nul > deployment.yaml
type nul > service.yaml
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
kubectl get deployments
kubectl get pods
kubectl get services
kubectl port-forward service/ia1-service 9082:80
kubectl scale deployment ia1-deployment --replicas=4
kubectl get pods
```

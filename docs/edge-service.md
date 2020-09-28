# QIoT Edge Service

* TOC
{:toc}

## How it work's


### Class Diagram

[![](https://mermaid.ink/img/eyJjb2RlIjoiY2xhc3NEaWFncmFtXG4gICAgU2Vuc29yIDx8LS0gUG9sbHV0aW9uUmVzdWx0XG4gICAgU2Vuc29yIDx8LS0gR2FzUmVzdWx0XG4gICAgU2Vuc29yIDogK2ludCBzdGF0aW9uSWRcbiAgICBjbGFzcyBQb2xsdXRpb25SZXN1bHR7XG4gICAgICArU3RyaW5nIGluc3RhbnRcbiAgICAgICtJbnRlZ2VyIFBNMTBcbiAgICAgICtJbnRlZ2VyIFBNMTBfYXRtXG4gICAgICArSW50ZWdlciBQTTFfMFxuICAgICAgK0ludGVnZXIgUE0xXzBfYXRtXG4gICAgICArSW50ZWdlciBQTTJfNVxuICAgICAgK0ludGVnZXIgUE0yXzVfYXRtXG4gICAgICArSW50ZWdlciBndDBfM3VtXG4gICAgICArSW50ZWdlciBndDBfNXVtXG4gICAgICArSW50ZWdlciBndDEwdW1cbiAgICAgICtJbnRlZ2VyIGd0MV8wdW1cbiAgICAgICtJbnRlZ2VyIGd0Ml81dW1cbiAgICAgICtJbnRlZ2VyIGd0NV8wdW1cbiAgICAgICt0b1N0cmluZygpXG4gICAgfVxuICAgIGNsYXNzIEdhc1Jlc3VsdHtcbiAgICAgICtTdHJpbmcgaW5zdGFudFxuICAgICAgK0RvdWJsZSBhZGNcbiAgICAgICtEb3VibGUgbmgzXG4gICAgICArRG91YmxlIG94aWRpc2luZ1xuICAgICAgK0RvdWJsZSByZWR1Y2luZ1xuICAgICAgK3RvU3RyaW5nKClcbiAgICB9XG4gICAgY2xhc3MgUmVzdWx0e1xuICAgICAgK0hhc2hNYXA8U3RyaW5nLE9iamVjdD5cbiAgICAgICt0b1N0cmluZygpXG4gICAgfVxuICAgIGNsYXNzIFN0YXRpb257XG4gICAgK0ludGVnZXIgaWRcbiAgICArU3RyaW5nIHNlcmlhbFxuICAgICtTdHJpbmcgbmFtZVxuICAgICtEb3VibGUgbG9uZ2l0dWRlXG4gICAgK0RvdWJsZSBsYXRpdHVkZVxuICAgICtCb29sZWFuIGFjdGl2ZVxuICAgIH0iLCJtZXJtYWlkIjp7InRoZW1lIjoiZGVmYXVsdCIsInRoZW1lVmFyaWFibGVzIjp7ImJhY2tncm91bmQiOiJ3aGl0ZSIsInByaW1hcnlDb2xvciI6IiNFQ0VDRkYiLCJzZWNvbmRhcnlDb2xvciI6IiNmZmZmZGUiLCJ0ZXJ0aWFyeUNvbG9yIjoiaHNsKDgwLCAxMDAlLCA5Ni4yNzQ1MDk4MDM5JSkiLCJwcmltYXJ5Qm9yZGVyQ29sb3IiOiJoc2woMjQwLCA2MCUsIDg2LjI3NDUwOTgwMzklKSIsInNlY29uZGFyeUJvcmRlckNvbG9yIjoiaHNsKDYwLCA2MCUsIDgzLjUyOTQxMTc2NDclKSIsInRlcnRpYXJ5Qm9yZGVyQ29sb3IiOiJoc2woODAsIDYwJSwgODYuMjc0NTA5ODAzOSUpIiwicHJpbWFyeVRleHRDb2xvciI6IiMxMzEzMDAiLCJzZWNvbmRhcnlUZXh0Q29sb3IiOiIjMDAwMDIxIiwidGVydGlhcnlUZXh0Q29sb3IiOiJyZ2IoOS41MDAwMDAwMDAxLCA5LjUwMDAwMDAwMDEsIDkuNTAwMDAwMDAwMSkiLCJsaW5lQ29sb3IiOiIjMzMzMzMzIiwidGV4dENvbG9yIjoiIzMzMyIsIm1haW5Ca2ciOiIjRUNFQ0ZGIiwic2Vjb25kQmtnIjoiI2ZmZmZkZSIsImJvcmRlcjEiOiIjOTM3MERCIiwiYm9yZGVyMiI6IiNhYWFhMzMiLCJhcnJvd2hlYWRDb2xvciI6IiMzMzMzMzMiLCJmb250RmFtaWx5IjoiXCJ0cmVidWNoZXQgbXNcIiwgdmVyZGFuYSwgYXJpYWwiLCJmb250U2l6ZSI6IjE2cHgiLCJsYWJlbEJhY2tncm91bmQiOiIjZThlOGU4Iiwibm9kZUJrZyI6IiNFQ0VDRkYiLCJub2RlQm9yZGVyIjoiIzkzNzBEQiIsImNsdXN0ZXJCa2ciOiIjZmZmZmRlIiwiY2x1c3RlckJvcmRlciI6IiNhYWFhMzMiLCJkZWZhdWx0TGlua0NvbG9yIjoiIzMzMzMzMyIsInRpdGxlQ29sb3IiOiIjMzMzIiwiZWRnZUxhYmVsQmFja2dyb3VuZCI6IiNlOGU4ZTgiLCJhY3RvckJvcmRlciI6ImhzbCgyNTkuNjI2MTY4MjI0MywgNTkuNzc2NTM2MzEyOCUsIDg3LjkwMTk2MDc4NDMlKSIsImFjdG9yQmtnIjoiI0VDRUNGRiIsImFjdG9yVGV4dENvbG9yIjoiYmxhY2siLCJhY3RvckxpbmVDb2xvciI6ImdyZXkiLCJzaWduYWxDb2xvciI6IiMzMzMiLCJzaWduYWxUZXh0Q29sb3IiOiIjMzMzIiwibGFiZWxCb3hCa2dDb2xvciI6IiNFQ0VDRkYiLCJsYWJlbEJveEJvcmRlckNvbG9yIjoiaHNsKDI1OS42MjYxNjgyMjQzLCA1OS43NzY1MzYzMTI4JSwgODcuOTAxOTYwNzg0MyUpIiwibGFiZWxUZXh0Q29sb3IiOiJibGFjayIsImxvb3BUZXh0Q29sb3IiOiJibGFjayIsIm5vdGVCb3JkZXJDb2xvciI6IiNhYWFhMzMiLCJub3RlQmtnQ29sb3IiOiIjZmZmNWFkIiwibm90ZVRleHRDb2xvciI6ImJsYWNrIiwiYWN0aXZhdGlvbkJvcmRlckNvbG9yIjoiIzY2NiIsImFjdGl2YXRpb25Ca2dDb2xvciI6IiNmNGY0ZjQiLCJzZXF1ZW5jZU51bWJlckNvbG9yIjoid2hpdGUiLCJzZWN0aW9uQmtnQ29sb3IiOiJyZ2JhKDEwMiwgMTAyLCAyNTUsIDAuNDkpIiwiYWx0U2VjdGlvbkJrZ0NvbG9yIjoid2hpdGUiLCJzZWN0aW9uQmtnQ29sb3IyIjoiI2ZmZjQwMCIsInRhc2tCb3JkZXJDb2xvciI6IiM1MzRmYmMiLCJ0YXNrQmtnQ29sb3IiOiIjOGE5MGRkIiwidGFza1RleHRMaWdodENvbG9yIjoid2hpdGUiLCJ0YXNrVGV4dENvbG9yIjoid2hpdGUiLCJ0YXNrVGV4dERhcmtDb2xvciI6ImJsYWNrIiwidGFza1RleHRPdXRzaWRlQ29sb3IiOiJibGFjayIsInRhc2tUZXh0Q2xpY2thYmxlQ29sb3IiOiIjMDAzMTYzIiwiYWN0aXZlVGFza0JvcmRlckNvbG9yIjoiIzUzNGZiYyIsImFjdGl2ZVRhc2tCa2dDb2xvciI6IiNiZmM3ZmYiLCJncmlkQ29sb3IiOiJsaWdodGdyZXkiLCJkb25lVGFza0JrZ0NvbG9yIjoibGlnaHRncmV5IiwiZG9uZVRhc2tCb3JkZXJDb2xvciI6ImdyZXkiLCJjcml0Qm9yZGVyQ29sb3IiOiIjZmY4ODg4IiwiY3JpdEJrZ0NvbG9yIjoicmVkIiwidG9kYXlMaW5lQ29sb3IiOiJyZWQiLCJsYWJlbENvbG9yIjoiYmxhY2siLCJlcnJvckJrZ0NvbG9yIjoiIzU1MjIyMiIsImVycm9yVGV4dENvbG9yIjoiIzU1MjIyMiIsImNsYXNzVGV4dCI6IiMxMzEzMDAiLCJmaWxsVHlwZTAiOiIjRUNFQ0ZGIiwiZmlsbFR5cGUxIjoiI2ZmZmZkZSIsImZpbGxUeXBlMiI6ImhzbCgzMDQsIDEwMCUsIDk2LjI3NDUwOTgwMzklKSIsImZpbGxUeXBlMyI6ImhzbCgxMjQsIDEwMCUsIDkzLjUyOTQxMTc2NDclKSIsImZpbGxUeXBlNCI6ImhzbCgxNzYsIDEwMCUsIDk2LjI3NDUwOTgwMzklKSIsImZpbGxUeXBlNSI6ImhzbCgtNCwgMTAwJSwgOTMuNTI5NDExNzY0NyUpIiwiZmlsbFR5cGU2IjoiaHNsKDgsIDEwMCUsIDk2LjI3NDUwOTgwMzklKSIsImZpbGxUeXBlNyI6ImhzbCgxODgsIDEwMCUsIDkzLjUyOTQxMTc2NDclKSJ9fSwidXBkYXRlRWRpdG9yIjpmYWxzZX0)](https://mermaid-js.github.io/mermaid-live-editor/#/edit/eyJjb2RlIjoiY2xhc3NEaWFncmFtXG4gICAgU2Vuc29yIDx8LS0gUG9sbHV0aW9uUmVzdWx0XG4gICAgU2Vuc29yIDx8LS0gR2FzUmVzdWx0XG4gICAgU2Vuc29yIDogK2ludCBzdGF0aW9uSWRcbiAgICBjbGFzcyBQb2xsdXRpb25SZXN1bHR7XG4gICAgICArU3RyaW5nIGluc3RhbnRcbiAgICAgICtJbnRlZ2VyIFBNMTBcbiAgICAgICtJbnRlZ2VyIFBNMTBfYXRtXG4gICAgICArSW50ZWdlciBQTTFfMFxuICAgICAgK0ludGVnZXIgUE0xXzBfYXRtXG4gICAgICArSW50ZWdlciBQTTJfNVxuICAgICAgK0ludGVnZXIgUE0yXzVfYXRtXG4gICAgICArSW50ZWdlciBndDBfM3VtXG4gICAgICArSW50ZWdlciBndDBfNXVtXG4gICAgICArSW50ZWdlciBndDEwdW1cbiAgICAgICtJbnRlZ2VyIGd0MV8wdW1cbiAgICAgICtJbnRlZ2VyIGd0Ml81dW1cbiAgICAgICtJbnRlZ2VyIGd0NV8wdW1cbiAgICAgICt0b1N0cmluZygpXG4gICAgfVxuICAgIGNsYXNzIEdhc1Jlc3VsdHtcbiAgICAgICtTdHJpbmcgaW5zdGFudFxuICAgICAgK0RvdWJsZSBhZGNcbiAgICAgICtEb3VibGUgbmgzXG4gICAgICArRG91YmxlIG94aWRpc2luZ1xuICAgICAgK0RvdWJsZSByZWR1Y2luZ1xuICAgICAgK3RvU3RyaW5nKClcbiAgICB9XG4gICAgY2xhc3MgUmVzdWx0e1xuICAgICAgK0hhc2hNYXA8U3RyaW5nLE9iamVjdD5cbiAgICAgICt0b1N0cmluZygpXG4gICAgfVxuICAgIGNsYXNzIFN0YXRpb257XG4gICAgK0ludGVnZXIgaWRcbiAgICArU3RyaW5nIHNlcmlhbFxuICAgICtTdHJpbmcgbmFtZVxuICAgICtEb3VibGUgbG9uZ2l0dWRlXG4gICAgK0RvdWJsZSBsYXRpdHVkZVxuICAgICtCb29sZWFuIGFjdGl2ZVxuICAgIH0iLCJtZXJtYWlkIjp7InRoZW1lIjoiZGVmYXVsdCIsInRoZW1lVmFyaWFibGVzIjp7ImJhY2tncm91bmQiOiJ3aGl0ZSIsInByaW1hcnlDb2xvciI6IiNFQ0VDRkYiLCJzZWNvbmRhcnlDb2xvciI6IiNmZmZmZGUiLCJ0ZXJ0aWFyeUNvbG9yIjoiaHNsKDgwLCAxMDAlLCA5Ni4yNzQ1MDk4MDM5JSkiLCJwcmltYXJ5Qm9yZGVyQ29sb3IiOiJoc2woMjQwLCA2MCUsIDg2LjI3NDUwOTgwMzklKSIsInNlY29uZGFyeUJvcmRlckNvbG9yIjoiaHNsKDYwLCA2MCUsIDgzLjUyOTQxMTc2NDclKSIsInRlcnRpYXJ5Qm9yZGVyQ29sb3IiOiJoc2woODAsIDYwJSwgODYuMjc0NTA5ODAzOSUpIiwicHJpbWFyeVRleHRDb2xvciI6IiMxMzEzMDAiLCJzZWNvbmRhcnlUZXh0Q29sb3IiOiIjMDAwMDIxIiwidGVydGlhcnlUZXh0Q29sb3IiOiJyZ2IoOS41MDAwMDAwMDAxLCA5LjUwMDAwMDAwMDEsIDkuNTAwMDAwMDAwMSkiLCJsaW5lQ29sb3IiOiIjMzMzMzMzIiwidGV4dENvbG9yIjoiIzMzMyIsIm1haW5Ca2ciOiIjRUNFQ0ZGIiwic2Vjb25kQmtnIjoiI2ZmZmZkZSIsImJvcmRlcjEiOiIjOTM3MERCIiwiYm9yZGVyMiI6IiNhYWFhMzMiLCJhcnJvd2hlYWRDb2xvciI6IiMzMzMzMzMiLCJmb250RmFtaWx5IjoiXCJ0cmVidWNoZXQgbXNcIiwgdmVyZGFuYSwgYXJpYWwiLCJmb250U2l6ZSI6IjE2cHgiLCJsYWJlbEJhY2tncm91bmQiOiIjZThlOGU4Iiwibm9kZUJrZyI6IiNFQ0VDRkYiLCJub2RlQm9yZGVyIjoiIzkzNzBEQiIsImNsdXN0ZXJCa2ciOiIjZmZmZmRlIiwiY2x1c3RlckJvcmRlciI6IiNhYWFhMzMiLCJkZWZhdWx0TGlua0NvbG9yIjoiIzMzMzMzMyIsInRpdGxlQ29sb3IiOiIjMzMzIiwiZWRnZUxhYmVsQmFja2dyb3VuZCI6IiNlOGU4ZTgiLCJhY3RvckJvcmRlciI6ImhzbCgyNTkuNjI2MTY4MjI0MywgNTkuNzc2NTM2MzEyOCUsIDg3LjkwMTk2MDc4NDMlKSIsImFjdG9yQmtnIjoiI0VDRUNGRiIsImFjdG9yVGV4dENvbG9yIjoiYmxhY2siLCJhY3RvckxpbmVDb2xvciI6ImdyZXkiLCJzaWduYWxDb2xvciI6IiMzMzMiLCJzaWduYWxUZXh0Q29sb3IiOiIjMzMzIiwibGFiZWxCb3hCa2dDb2xvciI6IiNFQ0VDRkYiLCJsYWJlbEJveEJvcmRlckNvbG9yIjoiaHNsKDI1OS42MjYxNjgyMjQzLCA1OS43NzY1MzYzMTI4JSwgODcuOTAxOTYwNzg0MyUpIiwibGFiZWxUZXh0Q29sb3IiOiJibGFjayIsImxvb3BUZXh0Q29sb3IiOiJibGFjayIsIm5vdGVCb3JkZXJDb2xvciI6IiNhYWFhMzMiLCJub3RlQmtnQ29sb3IiOiIjZmZmNWFkIiwibm90ZVRleHRDb2xvciI6ImJsYWNrIiwiYWN0aXZhdGlvbkJvcmRlckNvbG9yIjoiIzY2NiIsImFjdGl2YXRpb25Ca2dDb2xvciI6IiNmNGY0ZjQiLCJzZXF1ZW5jZU51bWJlckNvbG9yIjoid2hpdGUiLCJzZWN0aW9uQmtnQ29sb3IiOiJyZ2JhKDEwMiwgMTAyLCAyNTUsIDAuNDkpIiwiYWx0U2VjdGlvbkJrZ0NvbG9yIjoid2hpdGUiLCJzZWN0aW9uQmtnQ29sb3IyIjoiI2ZmZjQwMCIsInRhc2tCb3JkZXJDb2xvciI6IiM1MzRmYmMiLCJ0YXNrQmtnQ29sb3IiOiIjOGE5MGRkIiwidGFza1RleHRMaWdodENvbG9yIjoid2hpdGUiLCJ0YXNrVGV4dENvbG9yIjoid2hpdGUiLCJ0YXNrVGV4dERhcmtDb2xvciI6ImJsYWNrIiwidGFza1RleHRPdXRzaWRlQ29sb3IiOiJibGFjayIsInRhc2tUZXh0Q2xpY2thYmxlQ29sb3IiOiIjMDAzMTYzIiwiYWN0aXZlVGFza0JvcmRlckNvbG9yIjoiIzUzNGZiYyIsImFjdGl2ZVRhc2tCa2dDb2xvciI6IiNiZmM3ZmYiLCJncmlkQ29sb3IiOiJsaWdodGdyZXkiLCJkb25lVGFza0JrZ0NvbG9yIjoibGlnaHRncmV5IiwiZG9uZVRhc2tCb3JkZXJDb2xvciI6ImdyZXkiLCJjcml0Qm9yZGVyQ29sb3IiOiIjZmY4ODg4IiwiY3JpdEJrZ0NvbG9yIjoicmVkIiwidG9kYXlMaW5lQ29sb3IiOiJyZWQiLCJsYWJlbENvbG9yIjoiYmxhY2siLCJlcnJvckJrZ0NvbG9yIjoiIzU1MjIyMiIsImVycm9yVGV4dENvbG9yIjoiIzU1MjIyMiIsImNsYXNzVGV4dCI6IiMxMzEzMDAiLCJmaWxsVHlwZTAiOiIjRUNFQ0ZGIiwiZmlsbFR5cGUxIjoiI2ZmZmZkZSIsImZpbGxUeXBlMiI6ImhzbCgzMDQsIDEwMCUsIDk2LjI3NDUwOTgwMzklKSIsImZpbGxUeXBlMyI6ImhzbCgxMjQsIDEwMCUsIDkzLjUyOTQxMTc2NDclKSIsImZpbGxUeXBlNCI6ImhzbCgxNzYsIDEwMCUsIDk2LjI3NDUwOTgwMzklKSIsImZpbGxUeXBlNSI6ImhzbCgtNCwgMTAwJSwgOTMuNTI5NDExNzY0NyUpIiwiZmlsbFR5cGU2IjoiaHNsKDgsIDEwMCUsIDk2LjI3NDUwOTgwMzklKSIsImZpbGxUeXBlNyI6ImhzbCgxODgsIDEwMCUsIDkzLjUyOTQxMTc2NDclKSJ9fSwidXBkYXRlRWRpdG9yIjpmYWxzZX0)

### Pulling from qiot Sensor Service

Every **5s** the scheduler gather data from Sensor Service by Rest API.

``` java
package fr.axians.qiot.edge_service.service.sensor;

import javax.ws.rs.GET;
import javax.ws.rs.Path;
import javax.ws.rs.Produces;
import org.eclipse.microprofile.rest.client.inject.RegisterRestClient;

@Path("/sensors")
@RegisterRestClient
public interface SensorService {
    
    @GET
    @Path("/gas")
    @Produces("application/json")
    Result getGasResult();

    @GET
    @Path("/pollution")
    @Produces("application/json")
    Result getPollutionResult();
}
```
### Scheduling

The scheduling is done by **TelemetryService**. We get data from Sensor Service and put it on DataHub.

``` java
public class TelemetryService {
    
    private static final Logger LOGGER = Logger.getLogger("ListenerBean");
    @Inject
    SensorResource sr;

    
    /* Gas stream */
    @Outgoing("gas-stream")
    public Flowable <String> streamGasData() throws JsonProcessingException {
        
        /* Creating the ObjectMapper object */
        ObjectMapper mapper = new ObjectMapper();
        LOGGER.info(mapper.writeValueAsString(sr.getGas()));
        return Flowable.interval(5, TimeUnit.SECONDS).map(interval -> mapper.writeValueAsString(sr.getGas()));
    }


    /* Pollution stream */
    @Outgoing("pollution-stream")
    public Flowable <String> streamPollutionData() throws JsonProcessingException {
        /* Creating the ObjectMapper object */
        ObjectMapper mapper = new ObjectMapper();
        LOGGER.info(mapper.writeValueAsString(sr.getPollution()));
        /* Converting the Gas object to JSONString */
        return Flowable.interval(5, TimeUnit.SECONDS).map(interval ->  mapper.writeValueAsString(sr.getPollution()));
    }
}
```


### Shutdown

When we gracefully shutdown the QIoT Edge Service, the unregister is launched.

``` java
void onStop(@Observes ShutdownEvent ev) {
        LOGGER.info("Stop application begin uregistering process ...");               
        regService.unregStation(this.st.getId());
    }
```

### init overload

``` java
void init(){
        this.st = new Station();
        LOGGER.info(this.st.toString());
        
        //Defined the machine-id path to be able to regester
        java.nio.file.Path  path = Paths.get("/etc/machine-id");
        String content = null;

        //Get the id defined in the file
        try {
            content = Files.readString(path, StandardCharsets.UTF_8);
        } catch (IOException e) {
            LOGGER.error(e);
        };

        //Initialize the Station information
        this.st.setSerial(content);
        LOGGER.info("Device name : "+this.st.getName());

        /* Retrieve stationId and activate the station */
        Integer stationId =0;
        stationId = regService.regStation(this.st.getSerial(), this.st.getName(), this.st.getLongitude(), this.st.getLatitude());
        this.st.setId(stationId);
        this.st.setActive(true);
        LOGGER.info("Register ID : "+this.st.getId());
    }
```

1. Get the unique machine ID
1. Register the Device on DataHub

It's necessary to use the /etc/machine-id of Host machine and not ephemeral container. To do this, we share the host file with containers at the creation:

> podman **-v /etc/machine-id:/etc/machine-id:ro**  *[...]*

### (Un)Register

We created a *Interface* to Register and UnRegister Device on DataHub:

``` java
public interface RegistrationService {

    /* Registration of the station */
    @PUT
    @Path("/register/serial/{serial}/name/{name}/longitude/{longitude}/latitude/{latitude}")
    @Produces(MediaType.TEXT_PLAIN)
    @Consumes(MediaType.TEXT_PLAIN)
    public Integer regStation(@PathParam("serial") String serial,
    @PathParam("name") String name,
    @PathParam("longitude") Double longitude,
    @PathParam("latitude") Double latitude);

    /* Unregistration of the station */
    @DELETE
    @Path("/register/id/{id}")
    public void unregStation(@PathParam("id") Integer id);

}
```

name, longitude and latitude are set in application.properties and can be set by ENV variables from CRI. 

## Running the application in reel environment

From Fedora IOT on Raspberry PI, execute the following commands

### Env Variables

```
SENSORHOST: FQDN or IP of Python Sensor Service ex: (sensor)
TEAMNAME: Name of Edge Device or Team (default: fr_FR.UTF8)
TEAMLONGITUDE: Longitude of Device (default: -3.65)
TEAMLATITUDE: Latitude of Device (default: 47.09)
``` 

### Production

```
podman run \
-v /etc/machine-id:/etc/machine-id:ro \
-e SENSORHOST=changeme \
-e TEAMNAME=QIoT.fr_FR.UTF8 \
quay.io/acb-fr/qiot-edge-service-jvm:1.1
```

### Debug Mod

```
podman run \
-it --rm
-v /etc/machine-id:/etc/machine-id:ro \
quay.io/acb-fr/qiot-edge-service-jvm:1.1
```

## Contributors

<a href="https://github.com/QIoT-fr-FR-utf8/qiot-fr-fr-utf8.github.io/graphs/contributors">
  <img src="https://contributors-img.web.app/image?repo=QIoT-fr-FR-utf8/qiot-fr-fr-utf8.github.io" />
</a>
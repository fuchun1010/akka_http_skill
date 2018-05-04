
#### akka http response entity setting

```
import MediaTypes._
import org.json4s.JsonDSL._
import org.json4s.jackson.JsonMethods._
//complete(TagCalculateResponse(Info(400,s"""tag name :${tag.name} lacked necessary field""")))
val response = TagCalculateResponse(Info(400,s"""tag name :${tag.name} lacked necessary field"""))
val json = ("info" -> response.info.message)
complete(HttpResponse(StatusCodes.Accepted, entity = HttpEntity(`application/json` , compact(render(json)))))
```

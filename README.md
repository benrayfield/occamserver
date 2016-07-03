# occamserver
Minimalist server wrapping your func of bytes or map in and out

new Thread(new Occamserver(new MapFunc(

  public Map call(Map in){
  
    //String firstLineIn = Occamserver.asString(in.get("firstLine"));
    
    //byte contentIn[] = Occamserver.asBytes(in.get("content"));
    
  	Map out = new HashMap();
  	
  	out.put("firstLine", "HTTP/1.1 200 OK");
  	
  	out.put("content", "Occamserver. Time: "+System.currentTimeMillis()*.001+" seconds"); //byte[] or String
  	
    return out;
    
  }
  
))).start();

Then go to http://localhost

There are options for port, max bytes received, and max time receiving those bytes, per http request.

You can also use BytesFunc to get and return exact bytes (including http headers separated by \r\n).

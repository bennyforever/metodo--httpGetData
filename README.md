metodo--httpGetData
===================

ublic String httpGetData(String mURL) {
        String response="";
        mURL=mURL.replace(" ", "%20");
        Log.i("LocAndroid Response HTTP Threas","Ejecutando get 0: "+mURL);
        HttpClient httpclient = new DefaultHttpClient();

        Log.i("LocAndroid Response HTTP Thread","Ejecutando get 1");
        HttpGet httppost = new HttpGet(mURL);
        Log.i("LocAndroid Response HTTP Thread","Ejecutando get 2");
        try {


            Log.i("LocAndroid Response HTTP","Ejecutando get");
            // Execute HTTP Post Request
            ResponseHandler<String> responseHandler=new BasicResponseHandler();
            response = httpclient.execute(httppost,responseHandler); // linea donde falla 
            Log.i("LocAndroid Response HTTP",response);
        } catch (ClientProtocolException e) {
            Log.i("LocAndroid Response HTTP ERROR 1",e.getMessage());
            // TODO Auto-generated catch block
        } catch (IOException e) {
            Log.i("LocAndroid Response HTTP ERROR 2",e.getMessage());
            // TODO Auto-generated catch block
        }
        return response;

    }

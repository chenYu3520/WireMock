public class WeatherApplicationTest {
    @Rule
    public WireMockRule forecastIoService = new WireMockRule();

    private WeatherApplication weatherApplication = new WeatherApplication();

    @Before
    public void setUp() {
        weatherApplication.start();
    }

    @After
    public void tearDown() {
        weatherApplication.stop();
    }

    @Test
    public void servesWindSpeedBasedOnForecastIoResponse(){
        // TODO
        
   @Test
public void servesWindSpeedBasedOnForecastIoResponse() throws IOException {  
     forecastIoService.stubFor(get(urlEqualTo("/forecast/e67b0e3784104669340c3cb089412b67/51.507253,-0.127755"))
                .willReturn(aResponse().withBody("{\"currently\":{\"windSpeed\":12.34}}")));

    Content content = Request.Get("http://localhost:" + weatherApplication.port() + "/wind-speed")
             .execute()
             .returnContent();

        assertEquals("12.34mph", content.toString());
    }
    
    
https://github.com/wojciechbulaty/examples/tree/master/wiremock-weaither-application
https://www.petrikainulainen.net/programming/testing/wiremock-tutorial-introduction-to-stubbing/
https://dzone.com/articles/mocking-rest-api-with-wiremock-using-recording-mod
https://www.infoq.com/articles/Wiremock-testing-mocking-over-wire-stubs/
https://www.youtube.com/watch?v=M8HLPAF4i3M
https://www.infoq.com/articles/stubbing-mocking-service-virtualization-differences/
https://www.ontestautomation.com/getting-started-with-wiremock/https://developer.epages.com/blog/api-experience/how-to-mock-external-services-for-api-tests/
http://tirthal1.rssing.com/chan-29937020/latest.php#item21

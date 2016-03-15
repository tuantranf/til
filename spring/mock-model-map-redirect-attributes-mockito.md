# Mockito - Mock ModelMap & RedirectAttributes in jUnit testcase

## Mock ModelMap
```java
 @Test
  public void inputModelTest() throws Exception {
    ...
    ModelMap model = new ModelMap();
    
    String url = TestController.testModel(model, httpSession, httpServletResponse, redirectAttributes);
    
    assertEquals("message", model.get("message"));
  }
```

## Mock RedirectAttributes
```java
  @Test
  public void inputModelTest() throws Exception {
    ...
    RedirectAttributes redirectAttrs = new RedirectAttributesModelMap();

    String url = TestController.testRedirectAttributes(modelMap, httpSession, httpServletResponse, redirectAttrs);

    assertEquals("success", redirectAttrs.getFlashAttributes().get("messageType").toString());
```

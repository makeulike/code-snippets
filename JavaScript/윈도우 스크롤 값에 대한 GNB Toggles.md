

## mui.util with jQuery Use
```JavaScript

  var $pages = [
    $('#event1'),
    $('#event2'),
    $('#event3')
  ];
  var gnbIndex = 0;
  
   var toggleGNB = function() {
    var $gnb = $('gnbSelector');
    var $gnbElem = $('[data-toggle="scrollspy"]', $gnb);
    
    var offsetY = $(window).scrollTop(); // Possible to set variation values
    var util = mui.util;
    
    $gnbElem.removeClass('is-active');
    
    if ( mui.util.getBetween( offsetY, util.getOffset($pages[0]), util.getOffset($pages[0]) + util.getHeight($pages[0])) ) {
      gnbIndex = 0;
    } else if ( mui.util.getBetween( offsetY, util.getOffset($pages[1]), util.getOffset($pages[1]) + util.getHeight($pages[1])) ) {
      gnbIndex = 1;
    } else if ( mui.util.getBetween( offsetY, util.getOffset($pages[2]), util.getOffset($pages[2]) + util.getHeight($pages[2])) ) {
      gnbIndex = 2;
    } else if ( mui.util.getBetween( offsetY, util.getOffset($pages[3]), util.getOffset($pages[3]) + util.getHeight($pages[3])) ) {
      gnbIndex = 3;
    }

    $gnbElem.eq(gnbIndex).addClass('is-active');
  };
  
  
  var scrollInterface = function() {
    toggleGNB();
  };
  
  
  $(window).scroll(function() {
    scrollInterface();
  });
  
```

#Lost and found

###jquery get ajax

    $.ajax({
        url: 'http://example.com/page/2/',
        type: 'GET',
        success: function(data){ 
            $(data).find('#reviews .card').appendTo('#reviews');
        },
        error: function(data) {
            alert('woops!'); //or whatever
        }
    });


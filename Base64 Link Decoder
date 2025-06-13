// ==UserScript==
// @name         Base64 Link Decoder 
// @version      1.1
// @description  Decode highlighted Base64 text to UTF-8 and open a webpage with the decoded text when the "a" key is pressed (Only works on specific URL pattern)
// @match        
// @match        
// @match        
// @author       CalbeeDaLock
// ==/UserScript==

(function() {
    'use strict';

    // Create a button element
    const button = document.createElement('button');
    button.innerText = 'Decode Base64 and Open Webpage';
    document.body.appendChild(button);

    // Add event listener to the button
    button.addEventListener('click', decodeBase64AndOpenWebpage);

    function decodeBase64AndOpenWebpage() {
        // Get the highlighted text
        const selectedText = window.getSelection().toString();

        if (selectedText) {
            let decodedText;
            try {
                if (selectedText.startsWith('aHR0')) {
                    // Decode the Base64 text to UTF-8
                    decodedText = atob(selectedText);
                } else if (selectedText.startsWith('HR0')) {
                    // Decode the Base64 text to UTF-8
                    decodedText = atob('a' + selectedText);
                } else if (selectedText.startsWith('YUhSM')) {
                    // Decode the Base64 text to UTF-8 twice
                    decodedText = atob(atob(selectedText));
                } else if (selectedText.startsWith('WVVoU')) {
                    // Decode the Base64 text to UTF-8 three times
                    decodedText = atob(atob(atob(selectedText)));
                } else if (selectedText.startsWith('V1ZWb')) {
                    // Decode the Base64 text to UTF-8 four times
                    decodedText = atob(atob(atob(atob(selectedText))));
                } else {
                    throw new Error('Unsupported Base64 format');
                }

                // Open a new webpage with the decoded text
                window.open(decodedText);
            } catch (error) {
                console.error('Error decoding Base64:', error);
                alert('Error decoding Base64: ' + error.message);
            }
        }
    }

    // Add event listener to detect the "a" key press
    document.addEventListener('keydown', function(event) {
        if (event.key === 'a') {
            decodeBase64AndOpenWebpage();
        }
    });
})();

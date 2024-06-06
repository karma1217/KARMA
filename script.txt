var tablinks = document.getElementsByClassName("tab-links");
var tabcontents = document.getElementsByClassName("tab-contents");

function opentab(tabname, event) {
    for (let tablink of tablinks) {
        tablink.classList.remove("active-link");
    }
    for (let tabcontent of tabcontents) {
        tabcontent.classList.remove("active-tab");
    }
    event.currentTarget.classList.add("active-link");
    document.getElementById(tabname).classList.add("active-tab");
}

// JavaScript: Add functionality to open the sidebar when the menu icon is clicked
function openmenu() {
    document.getElementById("sidemenu").style.right = "0"; // Display the sidebar by setting its right position to 0
}

// JavaScript: Add functionality to close the sidebar when the close button is clicked
function closemenu() {
    document.getElementById("sidemenu").style.right = "-200px"; // Hide the sidebar by moving it to the left
}


$('.slide').hiSlide();


document.addEventListener("DOMContentLoaded", function() {
    // Get all modal elements
    var modals = document.querySelectorAll(".modal");

    // Get all images triggering modals
    var imgs = document.querySelectorAll(".myImg");

    // Loop through each image to attach click event
    imgs.forEach(function(img, index) {
        img.addEventListener("click", function() {
            // Show the corresponding modal
            modals[index].style.display = "block";

            // Set modal image source and caption
            var modalImg = modals[index].querySelector(".modal-img");
            modalImg.src = this.src;
            var caption = modals[index].querySelector(".caption");
            caption.innerHTML = this.alt;
        });
    });

    // Get all close buttons
    var closeBtns = document.querySelectorAll(".close");

    // Loop through each close button to attach click event
    closeBtns.forEach(function(btn) {
        btn.addEventListener("click", function() {
            // Hide the modal when close button is clicked
            var modal = this.parentElement.parentElement;
            modal.style.display = "none";
        });
    });

    // Close modal when user clicks outside of modal content
    window.addEventListener("click", function(event) {
        modals.forEach(function(modal) {
            if (event.target == modal) {
                modal.style.display = "none";
            }
        });
    });
});

function openModal(modalId) {
    var modal = document.getElementById(modalId);
    modal.style.display = "block";
}

function closeModal(modalId) {
    var modal = document.getElementById(modalId);
    modal.style.display = "none";
}
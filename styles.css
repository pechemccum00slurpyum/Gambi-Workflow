// Back to Dashboard function
function goBack() {
    window.location.href = "../index.html";
}

// Set up dragging and zoom functionality
let scale = 1; // Initial scale for zoom
let isPanning = false;
let startX, startY;
let translateX = 0, translateY = 0;

const flowchartContainer = document.getElementById("flowchartZoomContainer");

// Zoom in/out with mouse scroll
flowchartContainer.addEventListener("wheel", (event) => {
    event.preventDefault();
    if (event.deltaY < 0) {
        scale += 0.1; // Zoom in
    } else {
        scale = Math.max(0.5, scale - 0.1); // Zoom out with a minimum scale of 0.5
    }
    applyTransform();
});

// Start panning on left mouse button down
flowchartContainer.addEventListener("mousedown", (event) => {
    if (event.button === 0) { // Left-click detection
        isPanning = true;
        startX = event.clientX;
        startY = event.clientY;
        flowchartContainer.style.cursor = 'grabbing'; // Change cursor when dragging
    }
});

// Pan as mouse moves
flowchartContainer.addEventListener("mousemove", (event) => {
    if (!isPanning) return;
    event.preventDefault();
    const x = event.clientX - startX;
    const y = event.clientY - startY;
    translateX += x / scale; // Adjust panning speed based on current scale
    translateY += y / scale;
    startX = event.clientX;
    startY = event.clientY;
    applyTransform();
});

// Stop panning on mouse up or leave
flowchartContainer.addEventListener("mouseup", () => {
    isPanning = false;
    flowchartContainer.style.cursor = 'grab'; // Reset cursor when not dragging
});

flowchartContainer.addEventListener("mouseleave", () => {
    isPanning = false;
    flowchartContainer.style.cursor = 'grab'; // Reset cursor on leave
});

// Apply the current scale and translation values
function applyTransform() {
    flowchartContainer.style.transform = `scale(${scale}) translate(${translateX}px, ${translateY}px)`;
}

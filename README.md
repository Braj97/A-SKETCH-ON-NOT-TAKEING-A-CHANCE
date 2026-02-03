# A-SKETCH-ON-NOT-TAKEING-A-CHANCE
Ruby
require 'tk'

# Create window
root = TkRoot.new do
  title "Not Taking a Chance"
  geometry "800x500"
  background "white"
end

# Create canvas
canvas = TkCanvas.new(root) do
  width 800
  height 500
  bg "white"
  pack
end

# Draw ground / cliff
canvas.create_rectangle(0, 300, 800, 500,
  fill: "#cccccc", outline: "black")

# Cliff edge
canvas.create_line(400, 300, 400, 500,
  width: 4, fill: "black")

# Stick man (decision maker)
# Head
canvas.create_oval(260, 250, 290, 280,
  outline: "black")

# Body
canvas.create_line(275, 280, 275, 330,
  width: 2)

# Arms
canvas.create_line(275, 295, 250, 310, width: 2)
canvas.create_line(275, 295, 300, 310, width: 2)

# Legs
canvas.create_line(275, 330, 255, 360, width: 2)
canvas.create_line(275, 330, 295, 360, width: 2)

# Function to draw dice (risk)
def draw_dice(canvas, x, y)
  canvas.create_rectangle(x, y, x+40, y+40,
    fill: "white", outline: "black")
end

# Risky dice ahead
draw_dice(canvas, 440, 340)
draw_dice(canvas, 500, 380)
draw_dice(canvas, 560, 420)

# Message
canvas.create_text(200, 80,
  text: "Not every chance is worth taking",
  font: ["Arial", 18, "bold"],
  fill: "black")

canvas.create_text(220, 120,
  text: "Wisdom is knowing when to stop",
  font: ["Arial", 14],
  fill: "black")

# Run app
Tk.mainloop
#OUTPUTS

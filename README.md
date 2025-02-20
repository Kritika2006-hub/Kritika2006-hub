-import numpy as np
import matplotlib.pyplot as plt
import matplotlib.colors as mcolors

def plot_led_brightness(brightness_percentage):
    """
    This function plots a graph representing the LED with varying brightness.
    
    Parameters:
        brightness_percentage (int): A percentage value to control the LED brightness from 0 to 100.
    """
    
    # Generate a color map based on the brightness percentage (from black to bright color)
    brightness_intensity = brightness_percentage / 100.0  # Scale percentage to [0, 1]
    
    # Define the color (R, G, B) depending on brightness, simulate LED color with intensity
    color = (brightness_intensity, brightness_intensity, brightness_intensity)  # Example: grayscale
    
    # Create a plot
    fig, ax = plt.subplots(figsize=(5, 5))
    
    # Create a square that will represent the LED light with the given brightness color
    ax.add_patch(plt.Rectangle((0, 0), 1, 1, color=color))
    
    # Add text for brightness level
    ax.text(0.5, 0.5, f'{brightness_percentage}% brightness', color='white', 
            ha='center', va='center', fontsize=12, weight='bold')
    
    # Remove axes for better visualization
    ax.set_xticks([])
    ax.set_yticks([])
    
    # Title
    ax.set_title(f"LED Brightness: {brightness_percentage}%")
    
    # Display the plot
    plt.show()

def show_brightness_levels():
    """
    This function creates different graphs for various LED brightness levels (0% to 100%).
    """
    # Set up different brightness levels (from 0% to 100%)
    brightness_levels = [0, 20, 40, 60, 80, 100]
    
    # Plot each brightness level
    for level in brightness_levels:
        plot_led_brightness(level)

# Call the function to show the LED brightness levels
show_brightness_levels()

3D Reconstruction from Single Image
Project Description:-
This project demonstrates a basic framework for reconstructing a 3D mesh from a single 2D image using a deep learning model implemented with PyTorch and PyTorch3D.
Features.

Load and preprocess a single 2D image (from URL or local path).
Utilize a trained PyTorch model to predict 3D vertex coordinates from the image features.
Construct a 3D mesh from the predicted vertices and predefined face information.
Visualize the reconstructed 3D mesh from multiple viewpoints using PyTorch3D's renderer.
Save the reconstructed mesh to an OBJ file format.
Display the reconstructed mesh interactively using trimesh and pyglet.

Requirements:-

torch==2.0.1+cu118
torchvision==0.15.2+cu118
pytorch3d (installed from git+https://github.com/facebookresearch/pytorch3d.git)
requests
matplotlib
scikit-image
trimesh
pyglet

Installation:-

Clone this repository (if applicable, otherwise skip this step).
Install the required libraries using pip:!pip install torch==2.0.1+cu118 torchvision==0.15.2+cu118 --extra-index-url https://download.pytorch.org/whl/cu118
!pip install "git+https://github.com/facebookresearch/pytorch3d.git"
!pip install requests matplotlib scikit-image trimesh pyglet
Note: The specific PyTorch and PyTorch3D versions are crucial for compatibility.

Usage:-

Ensure you have the required libraries installed.
Make sure you have a trained model saved as model.pth in a directory named models in the same directory as your notebook or script, or modify the code to point to your model file.
Use the reconstruct_3d function to perform the 3D reconstruction:from your_module import reconstruct_3d # Assuming the functions are in a module

image_url = "YOUR_IMAGE_URL_OR_PATH"
output_mesh = reconstruct_3d(image_url)

Visualize the reconstructed mesh using the visualize_mesh function:from your_module import visualize_mesh # Assuming the functions are in a module
visualize_mesh(output_mesh)

The mesh is automatically saved as output.obj. You can also display it interactively:import trimesh
from IPython.display import HTML
mesh = trimesh.load('output.obj')
html = mesh.show(background=(255,255,255))
display(HTML(html.data))


Example:-
# Example image URL
image_url = "https://pngimg.com/uploads/circle/circle_PNG75.png"

# Run reconstruction:-
output_mesh = reconstruct_3d(image_url)

# Visualize results:-
visualize_mesh(output_mesh)

# Display interactively:-
import trimesh
from IPython.display import HTML
mesh = trimesh.load('output.obj')
html = mesh.show(background=(255,255,255))
display(HTML(html.data))

Evaluation:-

The primary method of evaluation is visual inspection of the reconstructed 3D mesh. The visualize_mesh function renders the mesh from different angles, allowing you to assess the quality and accuracy of the reconstruction. Additionally, you can examine the generated output.obj file in a 3D viewer to further evaluate the mesh structure and vertex positions.

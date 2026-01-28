# VTK Notes


If you want to write points to Polydata, you just need to put them in a `vtkPoints` object first.

```python
# display points for debugging
updated_points = vtk.vtkPoints()
updated_points.SetData(numpy_support.numpy_to_vtk(rad_points))
updated_points_polydata = vtk.vtkPolyData()
updated_points_polydata.SetPoints(updated_points)

# not sure why this is needed, but points won't render without it
vertices = vtk.vtkCellArray()
for i in range(updated_points.GetNumberOfPoints()):
	vertices.InsertNextCell(1)
	vertices.InsertCellPoint(i)
updated_points_polydata.SetVerts(vertices)
```


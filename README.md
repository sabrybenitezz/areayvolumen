# areayvolumen
principios SOLID
Dado el siguiente código:

public interface IShape
{
    int Width { get; set; }
    double GetArea();
    double GetVolume();
}

public class Sqaure : IShape
{
    private int width;
    public Sqaure()
    {
    }

    public int Width
    {
        get { return width; }
        set { width = value; }
    }

    public double GetArea()
    {
        double area = Width * Width;
        return area;
    }

    public double GetVolume()
    {
        throw new NotImplementedException();
    }
}

public class Cube : IShape
{
    private int width;
    public int Width
    {
        get { return width; }
        set { width = value; }
    }

    public double GetArea()
    {
        return 6 * Width * Width;
    }

    public double GetVolume()
    {
        return Width * Width * Width;
    }        
}

public interface IVolumeCalculator
{
    double CalculateVolume(IList shapes);
}

public class VolumeCalculator : IVolumeCalculator
{
    public double CalculateVolume(IList shapes)
    {
        double totalVolume = 0;
        foreach (var shape in shapes)
        {
            totalVolume += shape.GetVolume();
        }
        return totalVolume;
    }
}

Responder:
¿El código anterior infringe algún o algunos principios SOLID? En caso afirmativo, indicar cuales. En caso negativo, indicar qué principios cumple.
En caso que sea necesario, realizar las modificaciones necesarias en el código para que sigan las buenas prácticas indicadas en SOLID.

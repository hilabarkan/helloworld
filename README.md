# project
 
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Drawing;

namespace WindowsFormsApplication2
{
    public class Cube
    {
        public int number;
        public Color color;
        public Cube(int n, Color c)
        {
            this.number = n;
            this.color = c;
        }
        public override string ToString()
        {

            return number.ToString() + "," + color.ToString();
        }

        public static Cube Parse(string s)
        {
            string[] splitarray = s.Split(',');
            Cube c = new Cube(int.Parse(splitarray[0]), (Color)Enum.Parse(typeof(Color), splitarray[1]));
            return c;
        }

        public Bitmap Convert_Text_to_Image(int x, int y)
        {
            Bitmap bmp = new Bitmap(100, 100);
            using (Graphics graphics = Graphics.FromImage(bmp))
            {
                Font font = new Font("Ariel", 14);
                graphics.FillRectangle(Brushes.White, x, y, bmp.Width, bmp.Height);

                if (this.color == Color.RED)
                {
                    graphics.DrawString(this.number.ToString(), font, Brushes.Red, x, y);
                    graphics.Flush();
                    font.Dispose();
                    graphics.Dispose();
                }

                if (this.color == Color.BLACK)
                {
                    graphics.DrawString(this.number.ToString(), font, Brushes.Black, x, y);
                    graphics.Flush();
                    font.Dispose();
                    graphics.Dispose();
                }

                if (this.color == Color.BLUE)
                {
                    graphics.DrawString(this.number.ToString(), font, Brushes.BlueViolet, x, y);
                    graphics.Flush();
                    font.Dispose();
                    graphics.Dispose();
                }

                if (this.color == Color.YELLOW)
                {
                    graphics.DrawString(this.number.ToString(), font, Brushes.Yellow, x, y);
                    graphics.Flush();
                    font.Dispose();
                    graphics.Dispose();
                }
            }
            return bmp;
        }


    }
}

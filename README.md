# grafkom.github.io
#include <stdlib.h>
#include <GL/glut.h>

int is_depth;
static float ypoz = 0, zpoz = 0, xpoz = 0,a = 0, b = 0,c = -10;
void coba(int x1,int y1,int x2,int y2,int x3,int y3,int x4,int y4,int
z1,float z2,float z3){
glColor3f(0,1,0); //sisi depan
glVertex3d(x1,y1,z2);
glVertex3d(x2,y2,z2);
glVertex3d(x3,y3,z2);
glVertex3d(x4,y4,z2);
glColor3f(0,1,0);//right
glVertex3d(x2,y2,z2);
glVertex3d(x2,y2,z1);
glVertex3d(x3,y3,z1);
glVertex3d(x3,y3,z2);
glColor3f(0,1,0);//back
glVertex3d(x1,y1,z1);
glVertex3d(x2,y2,z1);
glVertex3d(x3,y3,z1);
glVertex3d(x4,y4,z1);
glColor3f(0,1,0);//left
glVertex3d(x1,y1,z2);
glVertex3d(x1,y1,z1);
glVertex3d(x4,y4,z1);
glVertex3d(x4,y4,z2);
glColor3f(1,0,0);//bottom
glVertex3d(x1,y1,z2);
glVertex3d(x2,y2,z2);
glVertex3d(x2,y2,z1);
glVertex3d(x1,y1,z1);
glColor3f(0,0,1);//top
glVertex3d(x3,y3,z2);
glVertex3d(x4,y4,z2);
glVertex3d(x4,y4,z1);
glVertex3d(x3,y3,z1);
}
void cobain(int x1,int y1,int x2,int y2,int x3,int y3,int x4,int
y4,float z1,float z2,float z3){ //atap
glColor3f(0,1,1);//kanan
glVertex3d(x3,y3,z1);
glVertex3d(x3,y3,z2);
glVertex3d(x3,y1,z3);
glColor3f(0,1,1);//kiri
glVertex3d(x4,y4,z2);
glVertex3d(x4,y4,z1);
glVertex3d(x4,y1,z3);
}

void cobaini(int x1,int y1,int x2,int y2,int x3,int y3,int x4,int
y4,float z1,float z2,float z3){//atap
glColor3f(0,0,0);//belakang
glVertex3d(x4,y4,z1);
glVertex3d(x3,y3,z1);
glVertex3d(x3,y1,z3);
glVertex3d(x4,y1,z3);
glColor3f(0,0,0);//depan
glVertex3d(x3,y3,z2);
glVertex3d(x4,y4,z2);
glVertex3d(x4,y1,z3);
glVertex3d(x3,y1,z3);
}

void init(void)
{
 glClearColor (1,1,1,1);
 glOrtho(-12,12,-6,6,-35,35);
 glEnable(GL_DEPTH_TEST);
 glShadeModel (GL_SMOOTH);
 glMatrixMode (GL_PROJECTION);
 glLoadIdentity ();
 gluPerspective(80.0,2.2, 1.0, 20.0);
 glMatrixMode (GL_MODELVIEW);
}
void display(void)
{
 glClear (GL_COLOR_BUFFER_BIT | GL_DEPTH_BUFFER_BIT);
glLoadIdentity (); 
glTranslatef(a,b,c); 
 glRotatef(xpoz,1,0,0);
glRotatef(ypoz,0,1,0);
 glRotatef(zpoz,0,0,1);
 glBegin(GL_QUADS);
//Rumah
coba(-8,-2,8,-2,8,2,-8,2,-5,3,0);//rumah
coba(2,-2,8,-2,8,2,2,2,-5,4,0);//kamar

 
 
 cobaini(-3,5,0,0,8,2,-8,2,-5.5,4.5,0);
glColor3f(1,0,0);//plafon depan
glVertex3d(8,1.8,-3);
glVertex3d(-8,1.8,-3);
glVertex3d(-8,1.8,4.5);
glVertex3d(8,1.8,4.5);//
glVertex3d(8,1.8,4.5);
glVertex3d(-8,1.8,4.5);
glVertex3d(-8,2,4.5);
glVertex3d(8,2,4.5);
glColor3f(1,0,0);//plafon belakang
glVertex3d(8,1.8,-5.5);
glVertex3d(-8,1.8,-5.5);
glVertex3d(-8,1.8,4.5);
glVertex3d(8,1.8,4.5);
glVertex3d(8,1.8,-5.5);
glVertex3d(-8,1.8,-5.5);
glVertex3d(-8,2,-5.5);
glVertex3d(8,2,-5.5);
glColor3f(1,1,1);
glVertex3d(4,-0.5,4.1);//cendela kamar
glVertex3d(6,-0.5,4.1);
glVertex3d(6,1,4.1);
glVertex3d(4,1,4.1);
glVertex3d(2.7,-0.5,4.1);//cendela kamar2
glVertex3d(3.8,-0.5,4.1);
glVertex3d(3.8,1,4.1);
glVertex3d(2.7,1,4.1);
glColor3f(0,0,1);
glVertex3d(-2,-2,3.05);//pintu depan
glVertex3d(2,-2,3.05);
glVertex3d(2,1.3,3.05);
glVertex3d(-2,1.3,3.05);
glVertex3d(-2,-2,-5.05);//pintu belakang
glVertex3d(2,-2,-5.05);
glVertex3d(2,1,-5.05);
glVertex3d(-2,1,-5.05);
glColor3f(1,1,1);
glVertex3d(-4.5,-1,3.05);//cendela rmh1 depan
glVertex3d(-2.5,-1,3.05);
glVertex3d(-2.5,1.3,3.05);
glVertex3d(-4.5,1.3,3.05);
glVertex3d(-6.5,-1,-5.05);//cendela rmh1 belakang
glVertex3d(-2.5,-1,-5.05);
glVertex3d(-2.5,1,-5.05);
glVertex3d(-6.5,1,-5.05);
glVertex3d(-7,-1,3.05);//cendela rmh2 depan
glVertex3d(-4.8,-1,3.05);
glVertex3d(-4.8,1.3,3.05);
glVertex3d(-7,1.3,3.05);
 glVertex3d(6.5,-1,-5.05);//cendela rmh2 belakang
glVertex3d(2.5,-1,-5.05);
glVertex3d(2.5,1,-5.05);
glVertex3d(6.5,1,-5.05);
 glEnd();
 glBegin(GL_TRIANGLES);
 cobain(-3,5,0,0,8,2,-8,2,-5.5,4.5,0);
 glEnd();
 glBegin(GL_LINES);
 glColor3f(0,0,0);
 glVertex3d(8,1.8,4.5);
glVertex3d(-8,1.8,4.5);
glVertex3d(-8,1.8,-5.5);
glVertex3d(8,1.8,-5.5);
glColor3f(1,0,0);
glVertex3d(-4.5,-1,-5.05);
glVertex3d(-4.5,1,-5.05);
glVertex3d(4.5,-1,-5.05);
glVertex3d(4.5,1,-5.05);
 glEnd();
 glutSwapBuffers(); 
}

void keyboard(unsigned char key, int x, int y)
{
 switch (key) {

case 'x':
xpoz=xpoz+5;
 if (xpoz>360) xpoz=0;
 glutPostRedisplay();
 break;
case 'y':
 ypoz=ypoz+5;
 if (ypoz>360) ypoz=0;
 glutPostRedisplay();
 break;
 case 'z':
 zpoz = zpoz+1;
 if (zpoz>360) zpoz=0;
 glutPostRedisplay();
 break;
case 'w':
b = b + 1;
glutPostRedisplay();
break;
case 's':
b = b - 1;
glutPostRedisplay();
break;
case 'a':
a = a - 1;
glutPostRedisplay();
break;
case 'd':
a = a + 1;
glutPostRedisplay();
break;
case 'q':
c = c + 1;
glutPostRedisplay();
break;
case 'e':
c = c - 1;
glutPostRedisplay();
break;
 }
}
void mouse(int button,int state,int x,int y);
void mouseMotion(int x, int y);
float xrot =0.0f;
float yrot =0.0f;
float xdiff =0.0f;
float ydiff =0.0f;
bool mouseDown = false;
void xx(){
	if (!mouseDown)
	{
		xrot += 0.3f;
		yrot += 0.4f;
	}
	glutPostRedisplay();
}
void mouse(int button, int state, int x,int y){
       if(button == GLUT_LEFT_BUTTON && state == GLUT_DOWN)
	   {
       mouseDown = true;
	   xdiff = x - yrot;
	   ydiff = -y + xrot;
	   }
	   else
		   mouseDown = false;
}
void mouseMontion(int x,int y)
{
	if(mouseDown)
	{
		yrot = x - xdiff;
		xrot = y + ydiff;

		glutPostRedisplay();
	}
}
int main(int argc, char** argv)
{
 glutInit(&argc, argv);
 glutInitDisplayMode (GLUT_RGB | GLUT_DEPTH | GLUT_DOUBLE);
 glutInitWindowSize (750, 500);
 glutInitWindowPosition (100, 100);
 glutCreateWindow("BRIAN RINANTO SAPUTRA - 672018065");
 init ();
 glutDisplayFunc(display);
 glutKeyboardFunc(keyboard);
 glutMouseFunc(mouse);
 glutMotionFunc(mouseMontion);
 glutMainLoop();
 return 0;
}

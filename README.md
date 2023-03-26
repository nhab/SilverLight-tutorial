# SilverLight-tutorial
Silverlight is a Microsoft old technology https://www.microsoft.com/silverlight/

:a deprecated  free browser plug-in for developing web/mobile app 	,mostly used for video/graphic capabilities
    :parts{
        1. Silverlight Plug-in			  		   : is the engine that renders the Silverlight application in the browser
            :Parts{
                The Presentation Engine with Multi Core support
                    Drawing Vector graphics and Shapes
                    PNG/JPG decoders
                    Image Cache, Text and Glyph cache
                    Animation System
                    3D rendering engine
                The XAML Parser
                Subset of the .NET Framework
                    Core Common Language Runtime (CLR)
                    The .NET base class libraries
                Media features
                    Media Pipeline
                    Download and streaming
                    Audio/video decoders
                Browser Interaction
                    HTML Bridge
                    Mouse and Keyboard Input and Events
                    Ink Support
                The Downloader

        2. Silverlight Host, the Web Page     : is the web page where Silverlight Application is hosted
            :ways of hosting the Silverlight Application{
                1. using <object> tag , in any HTML Page   
                    :X
                    <object data="data:application/x-silverlight-2," type="application/x-silverlight-2">
                    <param name="source" value="ClientBin/HelloWorld.xap" />
                    <param name="onError" value="onSilverlightError" />
                    <param name="background" value="white" />
                    <param name="minRuntimeVersion" value="4.0.50826.0" />
                    <param name="autoUpgrade" value="true" />
                    </object>
                2.  using a Silverlight Control ,in an ASPX Page    
                    -Visual Studio allows creating web projects that uses Silverlight User Controls in a webform.
                    -This user control is eventually converted into an object tag as shown in the earlier example
                    :X
                        <asp:Silverlight ID=”Xaml1” runat="”server”" Source=”HelloWorld.xap” Minimum- Version=”4.0.50826.0” Width=”100%” Height=”100%” />	 
                3.  using a MediaPlayer Control ,in an ASPX Page     
                    :X
                        <asp:MediaPlayer ID=”MediaPlayer1” runat="”server”" Height=”240px” Width=”320px”>	

        3. Silverlight Application File (.XAP)  : is the Internet Application which is developed using Microsoft Visual Studio and Expression Blend
            it is the file format of silverlight application
        4 .XAML : for specifying layout (it is a declarative language based on XML.)
            -Supports the dynamic compilation and execution of scripting languages like javascript
            -XAML files  the page: .xaml and The code behind: .xaml.cs
            -UserControl is the root element of the XAML file
            -silverlight allow two kinds of XAML templates in a silverlight project :
                - an Application template (<Application> tag ) 
                - and a User Control template with corresponding root elements.(<UserControl> tag)
            :X
                <!-- MainPage.xaml : -->
                <UserControl x:Class = "FirstExample.MainPage" 
                xmlns = "http://schemas.microsoft.com/winfx/2006/xaml/presentation" 
                xmlns:x = "http://schemas.microsoft.com/winfx/2006/xaml" 
                xmlns:d = "http://schemas.microsoft.com/expression/blend/2008" 
                xmlns:mc = "http://schemas.openxmlformats.org/markup-compatibility/2006" 
                mc:Ignorable = "d" 
                d:DesignHeight = "300" d:DesignWidth = "400"> 
                <Grid x:Name = "LayoutRoot" Background = "White"> 
                </Grid> 
                </UserControl>

                Description:
                
                You can see that the XAML file given above mentions different kinds of information; all of them are briefly described in the table given below.
                <UserControl 
                    Provides the base class for defining a new control that encapsulates the existing controls and provides its own logic.

                x:Class = "FirstExample.MainPage" 
                It is a partial class declaration, which connects the markup to that partial class code behind, defined in it.

                xmlns = "http://schemas.microsoft.com /winfx/2006/xaml/presentation" 	
                Maps the default XAML namespace for Silverlight client/framework.

                xmlns:x = "http://schemas.microsoft.c om/winfx/2006/xaml"
                XAML namespace for XAML language, which maps it to x: prefix.

                xmlns:d = "http://schemas.microsoft.com /expression/blend/2008" 	
                XAML namespace is intended for designer support, specifically designer support in the XAML design surfaces of Microsoft Visual Studio and Microsoft Expression Blend.

                xmlns:mc = "http://schemas.openxmlforma ts.org/markup-compatibility/2006" 
                Indicates and supports a markup compatibility mode for reading XAML.


    :TermoProcs{ 
        retained mode rendering  : the libraries retain a complete model of the objects to be rendered .
        Core presentation framework 
        :{
            Layout
                Enables dynamic positioning of UI elements.
                :{
                    Fixed Layout
                            Canvas element:
                            The simplest kind of layout is offered by the Canvas element.
                            The Canvas panel is the basic layout panel in which
                                the child elements can be positioned explicitly using the coordinates 
                                that are relative to any side of the Canvas such as left, right, top and bottom.
                            
                            Typically, the Canvas is used for 2D graphic elements (such as Ellipse, Rectangle etc.). 
                            It is not used for UI elements because specifying absolute coordinates give trouble when you resize, localize or scale your XAML application.
                            :X
                                <UserControl x:Class = "FirstExample.MainPage" 
                                xmlns = "http://schemas.microsoft.com/winfx/2006/xaml/presentation" 
                                xmlns:x = "http://schemas.microsoft.com/winfx/2006/xaml" 
                                xmlns:d = "http://schemas.microsoft.com/expression/blend/2008" 
                                xmlns:mc = "http://schemas.openxmlformats.org/markup-compatibility/2006" 
                                mc:Ignorable = "d" 
                                d:DesignHeight = "300" d:DesignWidth = "400">
                                
                                <Grid x:Name = "LayoutRoot" Background = "White"> 
                                    <Canvas Width = "380" Height = "280" > 
                                    <Ellipse Canvas.Left = "30" Canvas.Top = "30"  
                                        Fill = "Gray" Width = "200" Height = "120" />             
                                    </Canvas>  
                                </Grid>
                                    
                                </UserControl>
                    Dynamic Layouts
                        :meaning that the layouts can adapt as
                            the number of displayed items changes,
                            or the size of the displayed information varies,
                            or if the amount of space available to the application changes because the user has resized the browser.
                        :{
                            StackPanel : which arranges elements in a vertical or horizontal stack.
                            Grid 		: which provides a flexible grid-like, or table-like layout system which consists of rows and columns.
                :x
                    <UserControl x:Class = "DynamicLayout.MainPage" 
                    xmlns = "http://schemas.microsoft.com/winfx/2006/xaml/presentation" 
                    xmlns:x = "http://schemas.microsoft.com/winfx/2006/xaml" 
                    xmlns:d = "http://schemas.microsoft.com/expression/blend/2008" 
                    xmlns:mc = "http://schemas.openxmlformats.org/markup-compatibility/2006" 
                    mc:Ignorable = "d" 
                    d:DesignHeight = "300" d:DesignWidth = "400"> 
                    
                    <Grid x:Name = "LayoutRoot" Background = "White"> 
                        <StackPanel>
                        <Button x:Name = "button" Content = "Button" Margin = "10" /> 
                        <Button x:Name = "button1" Content = "Button" Margin = "10"/> 
                        <Button x:Name = "button2" Content = "Button" Margin = "10"/> 
                        <Button x:Name = "button3" Content = "Button" Margin = "10"/> 
                        </StackPanel>  
                    </Grid> 
                        
                    </UserControl> 

            UI Rendering
                Renders vector and bitmap graphics, animations, and text.
            UI Core 
                Vector animation & graphics
                Text images,text, animation, and images.

            input
                mouse
                keyboard
                ink
            Media
                Features playback and management of various types of audio and video files:

                    mp3

                    AAC

                    WMA

                    H.264

                    VC1

            

            Deep zoom
                :Enables you to zoom in on and pan around high resolution "images".
            Controls
                Supports extensible controls that are customizable through styling and templating.
            Template 	
                :describes the overall look and visual appearance of the control. 
                    For each control, there is a default template associated with it, which gives the appearance to that control.
                    :x
                    <UserControl x:Class = "ButtonTemplate.MainPage" 
                    xmlns = "http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
                    xmlns:x = "http://schemas.microsoft.com/winfx/2006/xaml" 
                    xmlns:d = "http://schemas.microsoft.com/expression/blend/2008" 
                    xmlns:mc = "http://schemas.openxmlformats.org/markup-compatibility/2006"  
                    mc:Ignorable = "d" d:DesignWidth = "640" d:DesignHeight = "480"> 
                    
                    <Grid x:Name = "LayoutRoot" HorizontalAlignment = "Center" 
                        VerticalAlignment = "Center">
                            
                        <Button Height = "100" Width = "100" Content = "Click!" 
                        HorizontalContentAlignment = "Left" Click = "button_Click">
                                
                        <Button.Template> 
                            <ControlTemplate TargetType = "Button"> 
                                <Grid> 
                                <Ellipse Fill = "Gray" Stroke = "Black" 	StrokeThickness = "3" Margin = "-64,0,0,0" /> 
                                <ContentPresenter HorizontalAlignment = "{TemplateBinding 
                                    HorizontalContentAlignment}" VerticalAlignment = "Center" 
                                    Content = "{TemplateBinding Content}" /> 
                                </Grid> 
                            </ControlTemplate>
                        </Button.Template>
                                
                        </Button>  
                            
                    </Grid> 
                        
                    </UserControl> 	
            Visual State
                :a change in color of a control  when the mouse is over it or an animation to shows that control is clickable.			
            DRM (digital rights management)

                Enables digital rights management of media assets

                

            Data binding

                Enables linking of data objects and UI elements.



        

        Browser host
            Integrated networking stack
            DOM Integration
            Application services
            Installer	
        - streaming media,
        - multimedia, graphics, and animation 
        -Silverlight is also one of the two application development platforms for Windows Phone,
            but web pages that use Silverlight cannot run on the Windows Phone or Windows Mobile versions of Internet Explorer, 
            as there is no Silverlight plugin for Internet Explorer on those platforms.


    
        -How to clean up silverlight cache?

            -to clean up silverlight cache : application installation>delete all

        -to clean up browser history: goto the internet option
        -Steps for rendering Silverlight on a web page
            The Plug-in acts in the following sequence when a user navigates to a Page with Silverlight :

            1-User opens a web page with Silverlight
            2-download XAP
                The page has embedded code which refers to a XAML Application (.XAP) file
                The Silverlight Plug-in is installed in the browser, and then downloads the .XAP file
            ->launch CLR
                Launch the embedded Common Language Runtime (CLR), the environment which ex- ecutes and manages the Silverlight application
            ->Extract XAML and dll(from XAP file)
            ->Load .NET(Assemblies)
            ->Create silverlight
                Create instances of the Silverlight Control that includes:
                    Creating a User Interface Element Tree
                    Managing the Layout of the User Interface
                    Drawing the User Interface
        -sample application : 
            can be easily created by 'new project' facility in visualsudio or blend.
            it generates these files:

            
            App.xaml
        
                <application xmlns=" http://schemas.microsoft.com/winfx/2006/xaml/presentation" xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml" x:class="HelloWorld.App">
                <application.resources>
                </application.resources></application>

            MainPage.xaml
            

                <UserControl x:class="HelloWorld.Page" xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation" xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml" width="400" height="300">
                <grid x:name="LayoutRoot" removed="AliceBlue">
                <textblock margin="120" fontsize="20">Hello World!</textblock>
                </grid>
                </UserControl>

            
            App.xaml.cs
                using System;
                using System.Windows;
                namespace HelloWorld {
                public partial class App : Application {
                public App() {
                this.Startup += this.Application_Startup;
                this.Exit += this.Application_Exit;
                this.UnhandledException += this.Application_UnhandledException; InitializeComponent();
                }
                private void Application_Startup(object sender, StartupEventArgs e) {
                this.RootVisual = new Page();
                }
                private void Application_Exit(object sender, EventArgs e){}
                private void Application_UnhandledException(object sender, ApplicationUnhandledExceptionEventArgs e) {
                if (!System.Diagnostics.Debugger.IsAttached)	{ e.Handled = true; Deployment.Current.Dispatcher.BeginInvoke(delegate{ReportErrorToDOM;});
                }
                }
                private void ReportErrorToDOM(ApplicationUnhandledExceptionEventArgs e) {
                try	{
                string errorMsg = e.ExceptionObject.Message +	11
                e.ExceptionObject.StackTrace;
                errorMsg = errorMsg.Replace('"', '\'').Replace("\r\n", @"\n"); System.Windows.Browser.HtmlPage.Window.Eval("throw new Error(\"Unhandled Error in Silverlight 2 Application " + errorMsg + "\");");
                }
                catch (Exception){}
                }
                }

            MainPage.xaml.cs
                using System;
                using System.Windows.Controls;
                namespace HelloWorld {
                public partial class Page : UserControl {
                public Page() { InitializeComponent();}
                }
                }



    :Tools 	: Silverlight Designer for Visual Studio 2010 and Expression Blend

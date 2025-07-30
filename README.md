\documentclass[10pt, letterpaper]{article}

% Packages:
\usepackage[
    ignoreheadfoot, % set margins without considering the header and footer
    top=2 cm, % separation between body and page edge from the top
    bottom=2 cm, % separation between body and page edge from the bottom
    left=2 cm, % separation between body and page edge from the left
    right=2 cm, % separation between body and page edge from the right
    footskip=1.0 cm, % separation between body and footer
    % showframe % for debugging 
]{geometry} % for adjusting page geometry
\usepackage{titlesec} % for customizing section titles
\usepackage{tabularx} % for making tables with fixed-width columns
\usepackage{array} % tabularx requires this
\usepackage[dvipsnames]{xcolor} % for coloring text
\definecolor{primaryColor}{RGB}{0, 0, 0} % define primary color
\usepackage{enumitem} % for customizing lists
\usepackage{fontawesome5} % for using icons
\usepackage{amsmath} % for math
\usepackage[
    pdftitle={Suhail's CV},
    pdfauthor={Suhail Siddiqui},
    pdfcreator={LaTeX with RenderCV},
    colorlinks=true,
    urlcolor=primaryColor
]{hyperref} % for links, metadata, and bookmarks
\usepackage[pscoord]{eso-pic} % for floating text on the page
\usepackage{calc} % for calculating lengths
\usepackage{bookmark} % for bookmarks
\usepackage{lastpage} % for getting the total number of pages
\usepackage{changepage} % for one-column entries (adjustwidth environment)
\usepackage{paracol} % for two and three-column entries
\usepackage{ifthen} % for conditional statements
\usepackage{needspace} % for avoiding page break right after the section title
\usepackage{iftex} % check if engine is pdflatex, xetex or luatex

% Ensure that the generate PDF is machine-readable/ATS parsable:
\ifPDFTeX
    \input{glyphtounicode}
    \pdfgentounicode=1
    \usepackage[T1]{fontenc}
    \usepackage[utf8]{inputenc}
    \usepackage{lmodern}
\fi

\usepackage{charter}

% Some settings:
\raggedright
\AtBeginEnvironment{adjustwidth}{\partopsep0pt} % remove space before adjustwidth environment
\pagestyle{empty} % no header or footer
\setcounter{secnumdepth}{0} % no section numbering
\setlength{\parindent}{0pt} % no indentation
\setlength{\topskip}{0pt} % no top skip
\setlength{\columnsep}{0.10cm} % set column seperation
\pagenumbering{gobble} % no page numbering

\titleformat{\section}{\needspace{4\baselineskip}\bfseries\large}{}{0pt}{}[\vspace{1pt}\titlerule]

\titlespacing{\section}{
    % left space:
    -1pt
}{
    % top space:
    0.1 cm
}{
    % bottom space:
    0.1 cm
} % section title spacing

\renewcommand\labelitemi{$\vcenter{\hbox{\small$\bullet$}}$} % custom bullet points
\newenvironment{highlights}{
    \begin{itemize}[
        topsep=0.1 cm,
        parsep=0.1 cm,
        partopsep=0pt,
        itemsep=0pt,
        leftmargin=0 cm + 10pt
    ]
}{
    \end{itemize}
} % new environment for highlights


\newenvironment{highlightsforbulletentries}{
    \begin{itemize}[
        topsep=0.1 cm,
        parsep=0.1 cm,
        partopsep=0pt,
        itemsep=0pt,
        leftmargin=10pt
    ]
}{
    \end{itemize}
} % new environment for highlights for bullet entries

\newenvironment{onecolentry}{
    \begin{adjustwidth}{
        0 cm + 0.00001 cm
    }{
        0 cm + 0.00001 cm
    }
}{
    \end{adjustwidth}
} % new environment for one-column entries

\newenvironment{twocolentry}[2][]{
    \onecolentry
    \def\secondColumn{#2}
    \setcolumnwidth{\fill, 4.5 cm}
    \begin{paracol}{2}
}{
    \switchcolumn \raggedleft \secondColumn
    \end{paracol}
    \endonecolentry
} % new environment for two-column entries

\newenvironment{threecolentry}[3][]{
    \onecolentry
    \def\thirdColumn{#3}
    \setcolumnwidth{, \fill, 4.5 cm}
    \begin{paracol}{3}
    {\raggedright #2} \switchcolumn
}{
    \switchcolumn \raggedleft \thirdColumn
    \end{paracol}
    \endonecolentry
} % new environment for three column entries

\newenvironment{header}{
    \setlength{\topsep}{0pt}\par\kern\topsep\centering\linespread{1.5}
}{
    \par\kern\topsep
} % new environment for the header

\newcommand{\placelastupdatedtext}{% \placetextbox{<horizontal pos>}{<vertical pos>}{<stuff>}
  \AddToShipoutPictureFG*{% Add <stuff> to current page foreground
    \put(
        \LenToUnit{\paperwidth-2 cm-0 cm+0.05cm},
        \LenToUnit{\paperheight-1.0 cm}
    ){\vtop{{\null}\makebox[0pt][c]{
        \small\color{gray}\textit{Last updated in September 2024}\hspace{\widthof{Last updated in September 2024}}
    }}}%
  }%
}%

% save the original href command in a new command:
\let\hrefWithoutArrow\href

% new command for external links:


\begin{document}
    \newcommand{\AND}{\unskip
        \cleaders\copy\ANDbox\hskip\wd\ANDbox
        \ignorespaces
    }
    \newsavebox\ANDbox
    \sbox\ANDbox{$|$}

        \begin{header}
            \fontsize{20 pt}{20 pt}\selectfont Suhail Siddiqui
        
            \vspace{0.5 pt}
        
            \normalsize
            \mbox{Rae Bareli}%
            \kern 5.0 pt%
            \AND%
            \kern 5.0 pt%
            \mbox{\hrefWithoutArrow{mailto:suhailsiddiqui1530@gmail.com}{suhailsiddiqui1530@gmail.com}}%
            \kern 5.0 pt%
            \AND%
            \kern 5.0 pt%
            \mbox{\hrefWithoutArrow{tel:+91-7311135785}{+91 7311135785}}%
            \kern 5.0 pt%
            \AND%
            \kern 5.0 pt%
            \mbox{\hrefWithoutArrow{https://suhail-sid.github.io/portfolio/}{Portfolio}}%
            \kern 5.0 pt%
            \AND%
            \kern 5.0 pt%
            \mbox{\hrefWithoutArrow{https://www.linkedin.com/in/suhail-siddiqui-9ba95a224/}{LinkedIn}}%
            \kern 5.0 pt%
            \AND%
            \kern 5.0 pt%
            \mbox{\hrefWithoutArrow{https://github.com/suhail-sid}{GitHub}}%
        \end{header}

    \vspace{5 pt - 0.3 cm}

 \section{Profile}
    
    \begin{onecolentry}
        A \textbf{Computer Science \& Engineering} student specializing in \textbf{Data Science and Artificial Intelligence}, with hands-on experience in \textbf{backend development}, \textbf{IoT integration}, and \textbf{secure data management}. Skilled in \textbf{Python}, \textbf{Django}, \textbf{JavaScript}, and creating \textbf{RESTful APIs}. Developed \textbf{AI-powered web solutions} and \textbf{real-time monitoring systems} with a strong focus on \textbf{usability} and \textbf{security}.

\vspace{0.1cm}

Internship experience at \textbf{Skyview Smart Solution} includes projects such as \textbf{Smart Farming} and \textbf{AI Medical Assistant}, involving \textbf{role-based access}, \textbf{IoT dashboards}, and \textbf{API infrastructure}. Contributed to backend systems with features like \textbf{WebSocket support} and \textbf{AI-based image processing}.

\vspace{0.1cm}

Passionate about using \textbf{technology} to solve real-world challenges efficiently and responsibly.

    \end{onecolentry}
    \vspace{0.1 cm}

    \section{Education}
        
        \begin{twocolentry}{
            Aug 2021 – May 2025
        }
            \textbf{Integral University, Lucknow}, B.Tech in Computer Science \& Engineering, Specialization in Data Science \& Artificial Intelligence (in association with IBM)
        \end{twocolentry}
        
        \vspace{0.1 cm}
        \begin{onecolentry}
            CGPA: 7.0
        \end{onecolentry}
        
        \vspace{0.1 cm}
        
        \begin{twocolentry}{
            Mar 2020 – Feb 2021
        }
            \textbf{St. Peter’s School, Raebareli}, Intermediate (PCM with CS)
        \end{twocolentry}
        
        \vspace{0.1 cm}
        \begin{onecolentry}
            Percentage: 80\%
        \end{onecolentry}
        
        \vspace{0.1 cm}
        
        \begin{twocolentry}{
            Mar 2018 – Feb 2019
        }
            \textbf{St. Peter’s School, Raebareli}, High School (Science)
        \end{twocolentry}
        
        \vspace{0.1 cm}
        \begin{onecolentry}
            Percentage: 68.3\%
        \end{onecolentry}
        

    \vspace{0.1 cm}

            
 \section{Experience}

\begin{twocolentry}{
    July 2025 – Present
}
    \textbf{Full Stack Python Developer}, Natlov Technologies Pvt. Ltd. -- Jharkhand
\end{twocolentry}

\begin{onecolentry}
        Technically manage the website of Columbia University, New York.
    \begin{highlights}
        \item Providing Technical Support to the University Website.
        \item Resolve the Issue(Tickets) raised by the management on Gitlab.
    \end{highlights}
\end{onecolentry}

\vspace{0.1cm}

\begin{twocolentry}{
    Dec 2024 – May 2025
}
    \textbf{Python Django Developer}, Skyview Smart Solutions -- Lucknow
\end{twocolentry}

\begin{onecolentry}
    \begin{highlights}
        \item \textbf{AI Medical Assistant:} Co-developed a secure Django-based diagnostic support system with role management and API-driven workflows.
        \item \textbf{Backend Development:} Built RESTful APIs using Django REST Framework with JWT authentication, unit testing, and error handling.
        \item \textbf{Virtual Try-On System:} Developed real-time backend with WebSocket (Socket.IO) support for syncing garment selections via mobile-triggered QR codes.
        \item \textbf{AI Integration:} Enabled camera-triggered image capture and overlay using AI modules (collaborated with \textbf{Deepak Anand Sir}).
        \item \textbf{Deployment:} Deployed APIs and WebSocket services on Windows IIS using ASGI and WSGI configurations.
        \item \textbf{Version Control:} Managed Git-based workflows and maintained technical documentation.
    \end{highlights}
\end{onecolentry}

\vspace{0.1cm}

\textbf{Python Django Intern}, Skyview Smart Solutions -- Lucknow \hfill Jan 2024 -- Jun 2024

\begin{onecolentry}
    Developed backend for a smart farming system integrating IoT sensors for real-time monitoring and automation of farm conditions.
    \begin{highlights}
        \item \textbf{Sensor Integration:} Processed real-time data from sensors via Firebase and MongoDB.
        \item \textbf{Automation:} Controlled farm equipment using logic based on incoming sensor data.
        \item \textbf{Access Control:} Designed dashboards with role-specific views for managers and workers.
        \item \textbf{Visualization:} Used Chart.js for interactive environmental trend analysis.
        \item \textbf{API Integration:} Created REST APIs for external platform compatibility and real-time decision support.
        \item \textbf{Optimization:} Improved database performance to ensure scalability under load.
    \end{highlights}
\end{onecolentry}

\vspace{0.1 cm}



    % \section{Publications}
        
    %     \begin{samepage}
    %         \begin{twocolentry}{
    %             Jan 2004
    %         }
    %             \textbf{3D Finite Element Analysis of No-Insulation Coils}
    %         \end{twocolentry}

    %         \vspace{0.1 cm}
            
    %         \begin{onecolentry}
    %             \mbox{Frodo Baggins}, \mbox{\textbf{\textit{Suhail Siddiqui}}}, \mbox{Samwise Gamgee}

    %             \vspace{0.1 cm}
                
    %     \href{https://doi.org/10.1109/TASC.2023.3340648}{10.1109/TASC.2023.3340648}
    %     \end{onecolentry}
    %     \end{samepage}
\section{Projects}

\begin{twocolentry}{
    \href{https://github.com/suhail-sid/smartmeter}{GitHub Repository}
}
    {\Large \textbf{Smart Meter}}
\end{twocolentry}

\vspace{0.1cm}
\begin{onecolentry}
Smart energy monitoring system for \textbf{real-time tracking} and \textbf{visualization} of electricity usage using \textbf{Python}, \textbf{Django}, and \textbf{IoT sensors}.
\begin{highlights}
    \item Collected data via \textbf{Arduino}, \textbf{ESP8266}, \textbf{ZMCT101C}/\textbf{ZMPT103B}, and synced readings using \texttt{.ino} scripts.
    \item Stored and processed data securely from \textbf{Firebase} to \textbf{MongoDB}.
    \item Calculated power using synchronized voltage-current timestamps.
    \item Built interactive frontend graphs with \textbf{JavaScript} and \textbf{Tailwind CSS}.
    \item Applied \textbf{role-based access control} and hosted in a private repo for confidentiality.
    \item \textbf{Received formal appreciation} from the \textbf{Assistant Professor} and \textbf{Associate Professor} for excellence in project contribution and innovation in sustainability-driven tech.

\end{highlights}
\textbf{Technologies:} Python, Django, Firebase, MongoDB, ESP8266, Arduino UNO, Tailwind CSS.
\end{onecolentry}

\vspace{0.2cm}

\begin{twocolentry}{
    \href{https://github.com/suhail-sid/student_management_project}{GitHub Repository}
}
    {\Large \textbf{College Management System}}
\end{twocolentry}

\vspace{0.1cm}
\begin{onecolentry}
Role-based academic platform built with \textbf{Python} and \textbf{Django} for managing student and faculty operations.
\begin{highlights}
    \item Supported roles: \textbf{HOD}, \textbf{Teacher}, \textbf{Student}, each with a custom dashboard.
    \item Included secure login, academic session handling, attendance, and grading.
    \item Provided clean setup via migrations and automated deployment.
\end{highlights}
\textbf{Technology Stack:} Python, Django, SQLite, HTML, CSS, JavaScript, Bootstrap.
\end{onecolentry}

\vspace{0.2cm}

\begin{twocolentry}{
    \href{https://github.com/suhail-sid/todo_list_project}{GitHub Repository}
}
    {\Large \textbf{To-Do List Web Application}}
\end{twocolentry}

\vspace{0.1cm}
\begin{onecolentry}
Simple task manager demonstrating core backend skills using \textbf{Django}.
\begin{highlights}
    \item Enabled intuitive \textbf{CRUD operations} for task management.
    \item Designed a responsive UI using \textbf{Bootstrap}.
    \item Used Django ORM for secure data handling.
\end{highlights}
\textbf{Technologies:} Python, Django, Bootstrap.
\end{onecolentry}

            \vspace{0.1 cm}
            
    \section{Technical Skills}
    
    \begin{itemize}
        \item \textbf{Languages:} Python, JavaScript, Basic Java, Basic C
        \item \textbf{Libraries / Frameworks:} Django, Django REST Framework, jQuery, Socket.IO, Tailwind CSS, Bootstrap, Chart.js
        \item \textbf{Tools / Platforms:} Git, VS Code, PyCharm, Arduino IDE, IIS Server, Firebase, Twilio, Overleaf, ThingsBoard
        \item \textbf{Cloud \& Deployment:} Windows IIS Server, ASGI, WSGI
        \item \textbf{Markup Languages:} HTML, CSS, LaTeX
        \item \textbf{Databases:} SQLite, MongoDB, MySQL, Firebase, pgAdmin4
    \end{itemize}

    \vspace{0.1 cm}

    \section{Certifications}

    \begin{itemize}
        \item \textbf{Experience Letter (5 months)} — \href{https://drive.google.com/file/d/1sAs9T4ZFEyx-k9EllzHLdjmj4Tnc6dax/view}{Skyview Smart Solution}
        \item \textbf{Skyview Internship Letter (3 months)} — \href{https://drive.google.com/file/d/1PWGY1KfIdmQRh8kUmq1gtAJhq8ENDSU5/view}{Skyview Smart Solution}
        \item \textbf{Letter of Appriciation (1 year)} — \href{https://drive.google.com/file/d/1w-UI9uDpAZuXYyjp-EopOtoUfiYtCOht/view}{Integral University}
        \item \textbf{Introduction To Industry 4.0 And Industrial Internet Of Things} — \href{https://drive.google.com/file/d/1_yb27NgstoYSrS5JxaEHfhZ-0MshVwjT/view}{NPTEL (SWAYAM)}
        \item \textbf{Skyview Internship Letter (5 months)} — \href{https://drive.google.com/file/d/1z6drbvdgIW01XLb7JCrOcKWpkquDKMaB/view}{Skyview Smart Solution}
        \item \textbf{Postman API Fundamentals - Student Expert} — \href{https://badgr.com/public/assertions/62Ps6cSVQl-DjXXzo6RiuA?identity__email=suhailsiddiqui1530@gmail.com}{Postman}
        \item \textbf{Introduction to Internet of Things (IoT)} — \href{https://drive.google.com/file/d/1yguhcDsNNvcchrdeep0CVnBgbsEj4AHJ/view}{NPTEL (SWAYAM)}
        \item \textbf{Web Development with Python} — \href{https://drive.google.com/file/d/1mAjJFcxWbqPuFp8F9pb0njRXFFnNZVUt/view}{Softlew Technologies}
        \item \textbf{Cybersecurity Fundamentals Badge} — \href{https://drive.google.com/file/d/1ewgcs2A8o3RKZfPmcDUQagQ_0EdLQEuE/view}{IBM Skills Build}
        \item \textbf{Cloud Computing Fundamentals} — \href{https://drive.google.com/file/d/1n5IwMHm0zRjxPV2CdzwWaPavMggM3ok9/view}{IBM Skills Build}
        \item \textbf{IBM Cognos Analytics V11.1.x Reporting Essentials} — \href{https://drive.google.com/file/d/15VJ4FB44uio6iUnktlzbXVQ4kUaamHua/view}{IBM Skills Build}
        \item \textbf{Rapid Development for AI} — \href{https://drive.google.com/file/d/16EvU3IHA3XXuu1MXlzCapIyOfPt0nfIq/view}{IBM Skills Build}
    \end{itemize}

    \vspace{0.1 cm}

    \section{Languages}

        \begin{itemize}
            \item \textbf{English} — Intermediate
            \item \textbf{Hindi} — Native
            \item \textbf{Urdu} — Fluent
        \end{itemize}

\end{document}
